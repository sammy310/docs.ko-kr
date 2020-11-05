---
title: 공용 언어 런타임의 형식 전달
description: 형식 전달을 사용하면 원본 어셈블리를 사용하는 애플리케이션을 다시 컴파일하지 않고도 형식을 다른 .NET 어셈블리로 이동할 수 있습니다.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687671"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="bf791-103">공용 언어 런타임의 형식 전달</span><span class="sxs-lookup"><span data-stu-id="bf791-103">Type forwarding in the common language runtime</span></span>

<span data-ttu-id="bf791-104">형식 전달을 사용하면 원본 어셈블리를 사용하는 애플리케이션을 다시 컴파일하지 않고도 형식을 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-104">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="bf791-105">예를 들어 애플리케이션이 *Utility.dll* 이라는 어셈블리에서 `Example` 클래스를 사용한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="bf791-105">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="bf791-106">*Utility.dll* 개발자는 어셈블리를 리팩터링하고 이 과정에서 `Example` 클래스를 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-106">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="bf791-107">이전 버전의 *Utility.dll* 이 새 버전의 *Utility.dll* 과 관련 어셈블리로 바뀌는 경우 `Example` 클래스를 사용하는 애플리케이션은 새 버전의 *Utility.dll* 에서 `Example` 클래스를 찾을 수 없기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-107">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="bf791-108">*Utility.dll* 개발자는 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> 특성을 사용하여 `Example` 클래스에 대한 요청을 전달하여 이를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-108">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="bf791-109">새 버전의 *Utility.dll* 에 이 특성이 적용된 경우 `Example` 클래스에 대한 요청은 현재 해당 클래스가 들어 있는 어셈블리로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-109">If the attribute has been applied to the new version of *Utility.dll* , requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="bf791-110">기존 애플리케이션은 다시 컴파일하지 않고도 정상적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-110">The existing application continues to function normally, without recompilation.</span></span>

## <a name="forward-a-type"></a><span data-ttu-id="bf791-111">형식 전달</span><span class="sxs-lookup"><span data-stu-id="bf791-111">Forward a type</span></span>

 <span data-ttu-id="bf791-112">다음 네 단계를 통해 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-112">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="bf791-113">형식의 소스 코드를 원본 어셈블리에서 대상 어셈블리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-113">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="bf791-114">해당 형식이 있었던 어셈블리에서 이동된 형식에 대해 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-114">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="bf791-115">다음 코드에서는 이동된 `Example` 형식의 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-115">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="bf791-116">해당 형식이 현재 들어 있는 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-116">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="bf791-117">해당 형식이 있었던 어셈블리를 현재 해당 형식이 들어 있는 어셈블리에 대한 참조를 사용하여 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-117">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="bf791-118">예를 들어 명령줄에서 C# 파일을 컴파일할 경우 [/reference(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-118">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="bf791-119">C++의 경우 소스 파일에서 [#using](/cpp/preprocessor/hash-using-directive-cpp) 지시문을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf791-119">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf791-120">참조</span><span class="sxs-lookup"><span data-stu-id="bf791-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="bf791-121">형식 전달(C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="bf791-121">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="bf791-122">#using 지시문</span><span class="sxs-lookup"><span data-stu-id="bf791-122">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
