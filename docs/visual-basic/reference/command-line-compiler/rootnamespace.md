---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: b6a2f3ba0772d8f8c8c6a762a1be01703d21b778
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403137"
---
# <a name="-rootnamespace"></a><span data-ttu-id="511e6-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="511e6-102">-rootnamespace</span></span>
<span data-ttu-id="511e6-103">모든 형식 선언에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="511e6-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="511e6-105">인수</span><span class="sxs-lookup"><span data-stu-id="511e6-105">Arguments</span></span>  
  
|<span data-ttu-id="511e6-106">용어</span><span class="sxs-lookup"><span data-stu-id="511e6-106">Term</span></span>|<span data-ttu-id="511e6-107">정의</span><span class="sxs-lookup"><span data-stu-id="511e6-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="511e6-108">현재 프로젝트에 대한 모든 형식 선언을 묶을 네임스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="511e6-109">설명</span><span class="sxs-lookup"><span data-stu-id="511e6-109">Remarks</span></span>  
 <span data-ttu-id="511e6-110">Visual Studio 실행 파일(Devenv.exe)을 사용하여 Visual Studio 통합 개발 환경에서 만든 프로젝트를 컴파일하는 경우 `-rootnamespace`를 사용하여 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 속성의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="511e6-111">자세한 내용은 [Devenv 명령줄 스위치](/visualstudio/ide/reference/devenv-command-line-switches)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="511e6-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="511e6-112">공용 언어 런타임 MSIL 디스어셈블러(`Ildasm.exe`)를 사용하여 출력 파일에서 네임스페이스 이름을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="511e6-113">Visual Studio 통합 개발 환경에서 -rootnamespace을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="511e6-114">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="511e6-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="511e6-116">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="511e6-117">3.  **루트 네임스페이스** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="511e6-118">예제</span><span class="sxs-lookup"><span data-stu-id="511e6-118">Example</span></span>  
 <span data-ttu-id="511e6-119">다음 코드는 `In.vb`를 컴파일하고 네임스페이스 `mynamespace`의 모든 형식 선언을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="511e6-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="511e6-120">참조</span><span class="sxs-lookup"><span data-stu-id="511e6-120">See also</span></span>

- [<span data-ttu-id="511e6-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="511e6-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="511e6-122">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="511e6-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="511e6-123">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="511e6-123">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
