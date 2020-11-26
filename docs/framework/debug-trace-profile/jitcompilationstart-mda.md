---
title: jitCompilationStart MDA (관리 디버깅 도우미)
description: JitCompilationStart MDA (관리 디버깅 도우미)는 JIT (just-in-time) 컴파일러가 .NET 함수 컴파일을 시작 하는 시기를 보고 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: 228226d90e70d296681e48ffe85dada8eb18209a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247371"
---
# <a name="jitcompilationstart-mda"></a>jitCompilationStart MDA

JIT(Just-In-Time) 컴파일러에서 함수 컴파일을 시작하는 시기를 보고하기 위해 `jitCompilationStart` MDA(관리 디버깅 도우미)가 활성화됩니다.  
  
## <a name="symptoms"></a>증상  

 작업 집합 크기는 mscorjit.dll 프로세스에 로드 되기 때문에 이미 네이티브 이미지 형식으로 된 프로그램에 대해 늘어납니다.  
  
## <a name="cause"></a>원인  

프로그램이 종속 된 모든 어셈블리가 네이티브 형식으로 생성 되지 않았거나 어셈블리가 올바르게 등록 되지 않았습니다.  

## <a name="resolution"></a>해결 방법  

 이 MDA를 사용 하면 JIT 컴파일되는 함수를 식별할 수 있습니다. 함수가 포함 된 어셈블리가 네이티브 형식으로 생성 되 고 제대로 등록 되었는지 확인 합니다.
  
## <a name="effect-on-the-runtime"></a>런타임에 미치는 영향  

 이 MDA는 메서드가 JIT 컴파일되기 직전의 메시지를 로깅하므로 이 MDA를 사용하면 성능에 상당한 영향을 미칩니다. 메서드가 인라인 인 경우이 MDA는 개별 메시지를 생성 하지 않습니다.  
  
## <a name="output"></a>출력  

 다음 코드 샘플은 샘플 출력을 표시합니다. 이 경우 출력은 어셈블리 테스트에서 "ns2.CO" 클래스의 "m" 메서드가 JIT 컴파일 되었음을 보여 줍니다.  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a>구성  

 다음 구성 파일은 처음 JIT 컴파일될 때 보고되는 메서드를 필터링하기 위해 사용할 수 있는 다양한 필터를 보여 줍니다. Name 특성의 값을로 설정 하 여 모든 메서드를 보고 하도록 지정할 수 있습니다 \* .  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>예제  

 다음 코드 샘플은 이전 구성 파일과 함께 사용됩니다.  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [관리 디버깅 도우미를 사용하여 오류 진단](diagnosing-errors-with-managed-debugging-assistants.md)
- [interop 마샬링](../interop/interop-marshaling.md)
