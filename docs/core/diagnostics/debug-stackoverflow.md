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
# <a name="debugging-stackoverflow-errors"></a><span data-ttu-id="9bace-103">StackOverflow 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="9bace-103">Debugging StackOverflow errors</span></span>

<span data-ttu-id="9bace-104"><xref:System.StackOverflowException>은 메서드 호출이 너무 많이 중첩되어 실행 스택이 오버플로하는 경우에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-104">A <xref:System.StackOverflowException> is thrown when when the execution stack overflows because it contains too many nested method calls.</span></span>  

<span data-ttu-id="9bace-105">예를 들어 다음과 같은 앱이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-105">For example, suppose you have an app as follows:</span></span>

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

<span data-ttu-id="9bace-106">Main 메서드는 스택 공간이 더 이상 없을 때까지 계속해서 자신을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-106">The Main method will continuously call itself until there is no more stack space.</span></span>  <span data-ttu-id="9bace-107">스택 공간이 더 이상 없으면 실행을 계속할 수 없으므로 <xref:System.StackOverflowException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-107">Once there is no more stack space, execution cannot continue and so it will throw a <xref:System.StackOverflowException>.</span></span>  

````
> dotnet run
Stack overflow.
````

> [!NOTE]
> <span data-ttu-id="9bace-108">.NET 5 이상에서는 호출 스택이 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-108">On .NET 5 and later, the callstack is output to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="9bace-109">이 문서에서는 lldb를 사용하여 스택 오버플로를 디버그하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-109">This article describes how to debug a stack overflow with lldb.</span></span> <span data-ttu-id="9bace-110">Windows에서 실행하는 경우 [Visual Studio](/visualstudio/debugger/what-is-debugging)나 [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)를 사용하여 앱을 디버그하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-110">If you are running on Windows, we suggest debugging the app with [Visual Studio](/visualstudio/debugger/what-is-debugging) or [Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging).</span></span>  

## <a name="example"></a><span data-ttu-id="9bace-111">예제</span><span class="sxs-lookup"><span data-stu-id="9bace-111">Example</span></span>

1. <span data-ttu-id="9bace-112">크래시에 대한 덤프를 수집하도록 구성하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-112">Run the app with it configured to collect a dump on crash</span></span>

    ````
    > export COMPlus_DbgEnableMiniDump=1
    > dotnet run
    Stack overflow.
    Writing minidump with heap to file /tmp/coredump.6412
    Written 58191872 bytes (14207 pages) to core file
    ````

2. <span data-ttu-id="9bace-113">[dotnet-sos](dotnet-sos.md)를 사용하여 SOS 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-113">Install the SOS extension using [dotnet-sos](dotnet-sos.md)</span></span>

    ````
    dotnet-sos install
    ````

3. <span data-ttu-id="9bace-114">LLDB에서 덤프를 디버그하여 실패한 스택을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-114">Debug the dump in lldb to see the failing stack</span></span>

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

4. <span data-ttu-id="9bace-115">맨 위 프레임 `0x00007f59b40900cc`가 여러 번 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-115">The top frame `0x00007f59b40900cc` is repeated several times.</span></span> <span data-ttu-id="9bace-116">[SOS](sos-debugging-extension.md) `ip2md` 명령을 사용하여 `0x00007f59b40900cc` 주소에 있는 메서드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-116">Use the [SOS](sos-debugging-extension.md) `ip2md` command to figure out what method is located at the `0x00007f59b40900cc` address</span></span>

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

5. <span data-ttu-id="9bace-117">표시된 메서드 temp.Program.Main(System.String[]) 및 소스 “/temp/Program.cs @ 9”를 살펴서 무엇을 잘못했는지 파악할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-117">Go look at the indicated method temp.Program.Main(System.String[]) and source "/temp/Program.cs @ 9" to see if you can figure out what you did wrong.</span></span> <span data-ttu-id="9bace-118">여전히 명확하지 않으면 코드의 해당 영역에 로깅을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bace-118">If it still wasn't clear you could add logging in that area of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bace-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bace-119">See Also</span></span>

* [<span data-ttu-id="9bace-120">.NET의 덤프 소개</span><span class="sxs-lookup"><span data-stu-id="9bace-120">An introduction to dumps in .NET</span></span>](dumps.md)
* [<span data-ttu-id="9bace-121">Linux 덤프 디버그</span><span class="sxs-lookup"><span data-stu-id="9bace-121">Debug Linux dumps</span></span>](debug-linux-dumps.md)
* [<span data-ttu-id="9bace-122">.NET용 SOS 디버깅 확장</span><span class="sxs-lookup"><span data-stu-id="9bace-122">SOS Debugging Extension for .NET</span></span>](sos-debugging-extension.md)
