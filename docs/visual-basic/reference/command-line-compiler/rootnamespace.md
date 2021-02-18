---
description: '자세한 정보: -rootnamespace'
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
ms.openlocfilehash: 0e034999a65bf5294e63c8f9cec1a4ce4de39a4b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474085"
---
# <a name="-rootnamespace"></a><span data-ttu-id="864ff-103">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="864ff-103">-rootnamespace</span></span>

<span data-ttu-id="864ff-104">모든 형식 선언에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-104">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864ff-105">구문</span><span class="sxs-lookup"><span data-stu-id="864ff-105">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="864ff-106">인수</span><span class="sxs-lookup"><span data-stu-id="864ff-106">Arguments</span></span>  
  
|<span data-ttu-id="864ff-107">용어</span><span class="sxs-lookup"><span data-stu-id="864ff-107">Term</span></span>|<span data-ttu-id="864ff-108">정의</span><span class="sxs-lookup"><span data-stu-id="864ff-108">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="864ff-109">현재 프로젝트에 대한 모든 형식 선언을 묶을 네임스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-109">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="864ff-110">설명</span><span class="sxs-lookup"><span data-stu-id="864ff-110">Remarks</span></span>  

 <span data-ttu-id="864ff-111">Visual Studio 실행 파일(Devenv.exe)을 사용하여 Visual Studio 통합 개발 환경에서 만든 프로젝트를 컴파일하는 경우 `-rootnamespace`를 사용하여 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 속성의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-111">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="864ff-112">자세한 내용은 [Devenv 명령줄 스위치](/visualstudio/ide/reference/devenv-command-line-switches)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="864ff-112">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="864ff-113">공용 언어 런타임 MSIL 디스어셈블러(`Ildasm.exe`)를 사용하여 출력 파일에서 네임스페이스 이름을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-113">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="864ff-114">Visual Studio 통합 개발 환경에서 -rootnamespace을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-114">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="864ff-115">1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="864ff-116">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="864ff-117">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="864ff-118">3.  **루트 네임스페이스** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="864ff-119">예제</span><span class="sxs-lookup"><span data-stu-id="864ff-119">Example</span></span>  

 <span data-ttu-id="864ff-120">다음 코드는 `In.vb`를 컴파일하고 네임스페이스 `mynamespace`의 모든 형식 선언을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="864ff-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="864ff-121">참조</span><span class="sxs-lookup"><span data-stu-id="864ff-121">See also</span></span>

- [<span data-ttu-id="864ff-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="864ff-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="864ff-123">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="864ff-123">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="864ff-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="864ff-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
