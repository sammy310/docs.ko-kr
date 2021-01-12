---
title: StackOverflow 오류 디버깅
description: StackOverflow 예외를 진단하는 방법 알아보기
ms.topic: tutorial
ms.date: 12/22/2020
ms.openlocfilehash: 92edf854ddcc2e778949d74eff1370cf27db25b4
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764931"
---
# <a name="debugging-stackoverflow-errors"></a>StackOverflow 오류 디버깅

<xref:System.StackOverflowException>은 메서드 호출이 너무 많이 중첩되어 실행 스택이 오버플로하는 경우에 throw됩니다.  

예를 들어 다음과 같은 앱이 있다고 가정합니다.

````
using System;

namespace temp
{
    class Program
    {
        static void Main(string[] args)
        {
            Main(args); // oops this recursion won't stop
        }
    }
}
````

Main 메서드는 스택 공간이 더 이상 없을 때까지 계속해서 자신을 호출합니다.  스택 공간이 더 이상 없으면 실행을 계속할 수 없으므로 <xref:System.StackOverflowException>을 throw합니다.  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> .NET 5 이상에서는 호출 스택이 콘솔에 출력됩니다.

> [!NOTE]
> 이 문서에서는 lldb를 사용하여 스택 오버플로를 디버그하는 방법을 설명합니다. Windows에서 실행하는 경우 [Visual Studio](/visualstudio/debugger/what-is-debugging)나 [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)를 사용하여 앱을 디버그하는 것이 좋습니다.  

## <a name="example"></a>예제

1. 크래시에 대한 덤프를 수집하도록 구성하여 앱을 실행합니다.

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. [dotnet-sos](dotnet-sos.md)를 사용하여 SOS 확장을 설치합니다.

    ````
    dotnet-sos install
    ````

3. LLDB에서 덤프를 디버그하여 실패한 스택을 확인합니다.

    ````
    lldb --core /temp/coredump.6412
    (lldb) bt
    ...
        frame #261930: 0x00007f59b40900cc
        frame #261931: 0x00007f59b40900cc
        frame #261932: 0x00007f59b40900cc
        frame #261933: 0x00007f59b40900cc
        frame #261934: 0x00007f59b40900cc
        frame #261935: 0x00007f5a2d4a080f libcoreclr.so`CallDescrWorkerInternal at unixasmmacrosamd64.inc:867
        frame #261936: 0x00007f5a2d3cc4c3 libcoreclr.so`MethodDescCallSite::CallTargetWorker(unsigned long const*, unsigned long*, int) at callhelpers.cpp:70
        frame #261937: 0x00007f5a2d3cc468 libcoreclr.so`MethodDescCallSite::CallTargetWorker(this=<unavailable>, pArguments=0x00007ffe8222e7b0, pReturnValue=0x0000000000000000, cbReturnValue=0) at callhelpers.cpp:604
        frame #261938: 0x00007f5a2d4b6182 libcoreclr.so`RunMain(MethodDesc*, short, int*, PtrArray**) [inlined] MethodDescCallSite::Call(this=<unavailable>, pArguments=<unavailable>) at callhelpers.h:468
    ...
    ````

4. 맨 위 프레임 `0x00007f59b40900cc`가 여러 번 반복됩니다. [SOS](sos-debugging-extension.md) `ip2md` 명령을 사용하여 `0x00007f59b40900cc` 주소에 있는 메서드를 확인합니다.

    ````
    (lldb) ip2md 0x00007f59b40900cc
    MethodDesc:   00007f59b413ffa8
    Method Name:          temp.Program.Main(System.String[])
    Class:                00007f59b4181d40
    MethodTable:          00007f59b4190020
    mdToken:              0000000006000001
    Module:               00007f59b413dbf8
    IsJitted:             yes
    Current CodeAddr:     00007f59b40900a0
    Version History:
      ILCodeVersion:      0000000000000000
      ReJIT ID:           0
      IL Addr:            0000000000000000
         CodeAddr:           00007f59b40900a0  (MinOptJitted)
         NativeCodeVersion:  0000000000000000
    Source file:  /temp/Program.cs @ 9
    ````

5. 표시된 메서드 temp.Program.Main(System.String[]) 및 소스 “/temp/Program.cs @ 9”를 살펴서 무엇을 잘못했는지 파악할 수 있는지 확인합니다. 여전히 명확하지 않으면 코드의 해당 영역에 로깅을 추가할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [.NET의 덤프 소개](dumps.md)
* [Linux 덤프 디버그](debug-linux-dumps.md)
* [.NET용 SOS 디버깅 확장](sos-debugging-extension.md)
