---
title: CLS 규격이 아닌 예외를 catch하는 방법
description: CLS 규격이 아닌 예외를 catch하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: db723cb1e29181e9462c5b423c66cdf8de659259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178673"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="6ebc7-104">CLS 규격이 아닌 예외를 catch하는 방법</span><span class="sxs-lookup"><span data-stu-id="6ebc7-104">How to catch a non-CLS exception</span></span>

<span data-ttu-id="6ebc7-105">C++/CLI를 포함한 일부 .NET 언어에서는 개체가 <xref:System.Exception>에서 파생되지 않은 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="6ebc7-106">이러한 예외를 *CLS 규격이 아닌 예외* 또는 *예외가 아닌 항목*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="6ebc7-107">C#에서는 CLS 규격이 아닌 예외를 throw할 수 없지만 다음 두 가지 방법으로 해당 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="6ebc7-108">`catch (RuntimeWrappedException e)` 블록 내에서.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="6ebc7-109">기본적으로 Visual C# 어셈블리는 CLS 규격이 아닌 예외를 래핑된 예외로 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="6ebc7-110"><xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 통해 액세스할 수 있는 원래 예외에 액세스해야 할 경우 이 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6ebc7-111">이 항목의 뒤에 나오는 절차에서는 이 방식으로 예외를 catch하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="6ebc7-112">일반 catch 블록(예외 형식이 지정되지 않은 catch 블록) 내에서 예외는 다른 모든 `catch` 블록 뒤에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="6ebc7-113">CLS 규격이 아닌 예외에 대한 응답으로 일부 작업(예: 로그 파일에 쓰기)을 수행하고자 하고 예외 정보에 액세스할 필요가 없는 경우 이 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="6ebc7-114">기본적으로 공용 언어 런타임은 모든 예외를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="6ebc7-115">이 동작을 사용하지 않으려면 일반적으로 AssemblyInfo.cs 파일에 있는 어셈블리 수준 특성 `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`를 코드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="6ebc7-116">CLS 규격이 아닌 예외를 catch하려면</span><span class="sxs-lookup"><span data-stu-id="6ebc7-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="6ebc7-117">`catch(RuntimeWrappedException e)` 블록 내에서 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 통해 원래 예외에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ebc7-118">예제</span><span class="sxs-lookup"><span data-stu-id="6ebc7-118">Example</span></span>  

 <span data-ttu-id="6ebc7-119">다음 예제에서는 C++/CLI로 작성된 클래스 라이브러리에서 throw된 CLS 규격이 아닌 예외를 catch하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="6ebc7-120">이 예제에서 C# 클라이언트 코드는 throw되는 예외 형식이 <xref:System.String?displayProperty=nameWithType>이라는 것을 사전에 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6ebc7-121">코드에서 해당 형식에 액세스할 수 있으면 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 다시 원래 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="6ebc7-122">참조</span><span class="sxs-lookup"><span data-stu-id="6ebc7-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="6ebc7-123">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="6ebc7-123">Exceptions and Exception Handling</span></span>](./index.md)
