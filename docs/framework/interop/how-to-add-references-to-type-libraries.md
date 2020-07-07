---
title: '방법: 형식 라이브러리에 참조 추가'
description: Visual Studio에서 또는 명령줄 컴파일을 위해 형식 라이브러리에 대한 참조를 추가하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
ms.openlocfilehash: a3c24385c9cc7debe95aa10369b050897415bc46
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617433"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="46bf9-103">방법: 형식 라이브러리에 참조 추가</span><span class="sxs-lookup"><span data-stu-id="46bf9-103">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="46bf9-104">Visual Studio에서는 형식 라이브러리에 참조를 추가하면 메타데이터가 포함된 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-104">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="46bf9-105">주 interop 어셈블리를 사용할 수 있는 경우 Visual Studio는 새 interop 어셈블리를 생성하기 전에 기존 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-105">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="46bf9-106">Visual Studio에서 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="46bf9-106">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="46bf9-107">Windows Setup.exe 파일이 자동으로 설치를 수행하는 경우가 아니라면 컴퓨터에 COM DLL 또는 EXE 파일을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="46bf9-107">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="46bf9-108">**프로젝트**, **참조 추가**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-108">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="46bf9-109">참조 관리자에서 **COM**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-109">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="46bf9-110">목록에서 형식 라이브러리를 선택하거나 .tlb 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-110">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="46bf9-111">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-111">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="46bf9-112">솔루션 탐색기에서 방금 추가한 참조에 대한 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-112">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="46bf9-113">**속성** 창에서 **Interop 형식 포함** 속성이 **True**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-113">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="46bf9-114">이 경우 Visual Studio가 COM 형식에 대한 형식 정보를 실행 파일에 포함하므로 앱과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-114">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46bf9-115">메뉴 및 대화 상자 옵션은 사용 중인 Visual Studio 버전에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-115">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="46bf9-116">명령줄 컴파일용으로 형식 라이브러리에 대한 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="46bf9-116">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="46bf9-117">[방법: 형식 라이브러리에서 Interop 어셈블리 생성](how-to-generate-interop-assemblies-from-type-libraries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46bf9-117">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="46bf9-118">interop 어셈블리 이름을 포함한 [-link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/link-compiler-option.md) 또는 [-link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 옵션을 사용하여 COM 형식에 대한 형식 정보를 실행 파일에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="46bf9-118">Use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bf9-119">참조</span><span class="sxs-lookup"><span data-stu-id="46bf9-119">See also</span></span>

- [<span data-ttu-id="46bf9-120">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="46bf9-120">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="46bf9-121">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="46bf9-121">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="46bf9-122">연습: Visual Studio에 관리되는 어셈블리의 형식 포함</span><span class="sxs-lookup"><span data-stu-id="46bf9-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="46bf9-123">-link(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="46bf9-123">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="46bf9-124">-link(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46bf9-124">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
