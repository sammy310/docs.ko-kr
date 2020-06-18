---
title: jitCompilationStart MDA
description: JIT (just-in-time) 컴파일러가 .NET 함수 컴파일을 시작 하는 시기를 보고 하기 위해 jitCompilationStart MDA (관리 디버깅 도우미)를 사용 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: bf2d09f433f0b8e4056fecd1f4e82bf3b91dd2bc
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904132"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="979e6-103">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="979e6-103">jitCompilationStart MDA</span></span>
<span data-ttu-id="979e6-104">JIT(Just-In-Time) 컴파일러에서 함수 컴파일을 시작하는 시기를 보고하기 위해 `jitCompilationStart` MDA(관리 디버깅 도우미)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-104">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="979e6-105">증상</span><span class="sxs-lookup"><span data-stu-id="979e6-105">Symptoms</span></span>  
 <span data-ttu-id="979e6-106">mscorjit.dll이 프로세스에 로드되므로 이미 네이티브 이미지 형식을 사용하는 프로그램용으로 작업 집합 크기가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-106">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="979e6-107">원인</span><span class="sxs-lookup"><span data-stu-id="979e6-107">Cause</span></span>  
 <span data-ttu-id="979e6-108">프로그램이 종속된 어셈블리 중 일부가 원시 형식으로 생성되지 않았거나 올바르게 등록되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-108">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="979e6-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="979e6-109">Resolution</span></span>  
 <span data-ttu-id="979e6-110">이 MDA를 사용하면 JIT 컴파일되는 함수를 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-110">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="979e6-111">함수가 포함된 어셈블리가 원시 형식으로 생성되어 적절하게 등록되었는지 판별합니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-111">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="979e6-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="979e6-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="979e6-113">이 MDA는 메서드가 JIT 컴파일되기 직전의 메시지를 로깅하므로 이 MDA를 사용하면 성능에 상당한 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-113">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="979e6-114">메서드가 인라인인 경우 이 MDA는 개별 메시지를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-114">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="979e6-115">출력</span><span class="sxs-lookup"><span data-stu-id="979e6-115">Output</span></span>  
 <span data-ttu-id="979e6-116">다음 코드 샘플은 샘플 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-116">The following code sample shows sample output.</span></span> <span data-ttu-id="979e6-117">이 경우 어셈블리 테스트에서 “ns2.CO” 클래스의 “m” 메서드가 JIT 컴파일되었음이 출력에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-117">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="979e6-118">구성</span><span class="sxs-lookup"><span data-stu-id="979e6-118">Configuration</span></span>  
 <span data-ttu-id="979e6-119">다음 구성 파일은 처음 JIT 컴파일될 때 보고되는 메서드를 필터링하기 위해 사용할 수 있는 다양한 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-119">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="979e6-120">Name 특성의 값을로 설정 하 여 모든 메서드를 보고 하도록 지정할 수 있습니다 \* .</span><span class="sxs-lookup"><span data-stu-id="979e6-120">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="979e6-121">예제</span><span class="sxs-lookup"><span data-stu-id="979e6-121">Example</span></span>  
 <span data-ttu-id="979e6-122">다음 코드 샘플은 이전 구성 파일과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="979e6-122">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="979e6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="979e6-123">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="979e6-124">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="979e6-124">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="979e6-125">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="979e6-125">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
