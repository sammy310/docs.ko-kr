---
title: Interop 프로젝트 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf0244060d3c5dfa39c220fc2d699a5f2f1fef9e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636208"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="c7f6d-102">Interop 프로젝트 컴파일</span><span class="sxs-lookup"><span data-stu-id="c7f6d-102">Compiling an Interop Project</span></span>

<span data-ttu-id="c7f6d-103">가져온 COM 형식이 포함된 하나 이상의 어셈블리를 참조하는 COM interop 프로젝트는 다른 관리되는 프로젝트와 마찬가지로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="c7f6d-104">Visual Studio 등의 개발 환경에서 interop 어셈블리를 참조하거나, 명령줄 컴파일러를 사용할 때 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="c7f6d-105">두 경우 모두, 제대로 컴파일하려면 interop 어셈블리가 다른 프로젝트 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="c7f6d-106">Interop 어셈블리를 참조하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-106">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="c7f6d-107">포함 interop 형식: [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 Visual Studio 2010부터 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="c7f6d-108">이것이 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-108">This is the recommended technique.</span></span>

- <span data-ttu-id="c7f6d-109">interop 어셈블리 배포: interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="c7f6d-110">이 경우 interop 어셈블리를 애플리케이션에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="c7f6d-111">이러한 두 방법 간의 차이점은 [관리 코드에서 COM 형식 사용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="c7f6d-112">Visual Studio에 interop 형식을 포함하는 방법은 [연습: Visual Studio에서 관리형 어셈블리의 형식 포함(C#)](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 및 [연습: Visual Studio에서 관리형 어셈블리의 형식 포함(Visual Basic)](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c7f6d-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), and [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span></span>

 <span data-ttu-id="c7f6d-113">명령줄 컴파일러를 사용하여 interop 어셈블리를 참조하고 실행 파일에 형식 정보를 포함하려면 [/link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [/link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="c7f6d-114">Visual C++ 애플리케이션은 형식 정보를 포함할 수 없지만 포함하는 애플리케이션이나 추가 기능과 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="c7f6d-115">배포될 때 주 interop 어셈블리를 포함하는 애플리케이션을 컴파일하려면 **/reference** 컴파일러 스위치를 사용하고 interop 어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f6d-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7f6d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7f6d-116">See also</span></span>

- [<span data-ttu-id="c7f6d-117">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="c7f6d-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="c7f6d-118">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c7f6d-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="c7f6d-119">[관리 코드에서 COM 형식 사용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c7f6d-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="c7f6d-120">연습: Visual Studio에서 관리형 어셈블리의 형식 포함(C#)</span><span class="sxs-lookup"><span data-stu-id="c7f6d-120">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)
- [<span data-ttu-id="c7f6d-121">연습: Visual Studio에서 관리형 어셈블리의 형식 포함(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7f6d-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="c7f6d-122">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="c7f6d-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
