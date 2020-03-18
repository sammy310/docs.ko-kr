---
title: 공용 언어 런타임의 형식 전달
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 215636a9617a2723d8ab69640c1d3e69491a7d87
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160367"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="b6a50-102">공용 언어 런타임의 형식 전달</span><span class="sxs-lookup"><span data-stu-id="b6a50-102">Type forwarding in the common language runtime</span></span>
<span data-ttu-id="b6a50-103">형식 전달을 사용하면 원본 어셈블리를 사용하는 애플리케이션을 다시 컴파일하지 않고도 형식을 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="b6a50-104">예를 들어 애플리케이션이 `Example`Utility.dll*이라는 어셈블리에서*  클래스를 사용한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b6a50-104">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="b6a50-105">*Utility.dll* 개발자는 어셈블리를 리팩터링하고 이 과정에서 `Example` 클래스를 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-105">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="b6a50-106">이전 버전의 *Utility.dll*이 새 버전의 *Utility.dll*과 관련 어셈블리로 바뀌는 경우 `Example` 클래스를 사용하는 애플리케이션은 새 버전의 `Example`Utility.dll*에서*  클래스를 찾을 수 없기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-106">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="b6a50-107">*Utility.dll* 개발자는 `Example` 특성을 사용하여 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> 클래스에 대한 요청을 전달하여 이를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-107">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="b6a50-108">새 버전의 *Utility.dll*에 이 특성이 적용된 경우 `Example` 클래스에 대한 요청은 현재 해당 클래스가 들어 있는 어셈블리로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-108">If the attribute has been applied to the new version of *Utility.dll*, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="b6a50-109">기존 애플리케이션은 다시 컴파일하지 않고도 정상적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6a50-110">.NET Framework 버전 2.0에서는 Visual Basic으로 작성된 어셈블리의 형식을 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="b6a50-111">그러나 Visual Basic으로 작성된 애플리케이션에서 전달된 형식을 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="b6a50-112">즉, 애플리케이션에서 C# 또는 C++로 코딩된 어셈블리를 사용하며 해당 어셈블리의 형식이 다른 어셈블리로 전달된 경우 Visual Basic 애플리케이션에서 전달된 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forward-types"></a><span data-ttu-id="b6a50-113">형식 전달</span><span class="sxs-lookup"><span data-stu-id="b6a50-113">Forward types</span></span>  
 <span data-ttu-id="b6a50-114">다음 네 단계를 통해 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-114">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="b6a50-115">형식의 소스 코드를 원본 어셈블리에서 대상 어셈블리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="b6a50-116">해당 형식이 있었던 어셈블리에서 이동된 형식에 대해 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="b6a50-117">다음 코드에서는 이동된 `Example` 형식의 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="b6a50-118">해당 형식이 현재 들어 있는 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-118">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="b6a50-119">해당 형식이 있었던 어셈블리를 현재 해당 형식이 들어 있는 어셈블리에 대한 참조를 사용하여 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="b6a50-120">예를 들어 명령줄에서 C# 파일을 컴파일할 경우 [/reference(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-120">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="b6a50-121">C++의 경우 소스 파일에서 [#using](/cpp/preprocessor/hash-using-directive-cpp) 지시문을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a50-121">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a50-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6a50-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="b6a50-123">형식 전달(C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="b6a50-123">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="b6a50-124">#using 지시문</span><span class="sxs-lookup"><span data-stu-id="b6a50-124">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
