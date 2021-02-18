---
description: '자세한 정보: -out(Visual Basic)'
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 82fb43ecf2239c38245f3afe7cacef8bad573175
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475892"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="dfee8-103">-out(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfee8-103">-out (Visual Basic)</span></span>

<span data-ttu-id="dfee8-104">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-104">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfee8-105">구문</span><span class="sxs-lookup"><span data-stu-id="dfee8-105">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="dfee8-106">인수</span><span class="sxs-lookup"><span data-stu-id="dfee8-106">Arguments</span></span>  
  
|<span data-ttu-id="dfee8-107">용어</span><span class="sxs-lookup"><span data-stu-id="dfee8-107">Term</span></span>|<span data-ttu-id="dfee8-108">정의</span><span class="sxs-lookup"><span data-stu-id="dfee8-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="dfee8-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="dfee8-109">Required.</span></span> <span data-ttu-id="dfee8-110">컴파일러에서 생성하는 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-110">The name of the output file the compiler creates.</span></span> <span data-ttu-id="dfee8-111">파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-111">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfee8-112">설명</span><span class="sxs-lookup"><span data-stu-id="dfee8-112">Remarks</span></span>  

 <span data-ttu-id="dfee8-113">생성할 파일의 전체 이름과 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-113">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="dfee8-114">이렇게 하지 않으면 .exe 파일은 `Sub Main` 프로시저를 포함하는 소스 코드 파일에서 해당 이름을 가져오고 .dll 파일은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-114">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="dfee8-115">.exe 또는 .dll 확장명 없이 파일 이름을 지정하면 `-target` 컴파일러 옵션에 지정된 값에 따라 컴파일러에서 자동으로 확장명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-115">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="dfee8-116">Visual Studio 통합 개발 환경에서 -out을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-116">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="dfee8-117">1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-117">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="dfee8-118">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-118">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="dfee8-119">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="dfee8-120">3.  **어셈블리 이름** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dfee8-121">예제</span><span class="sxs-lookup"><span data-stu-id="dfee8-121">Example</span></span>  

 <span data-ttu-id="dfee8-122">다음 코드는 `T2.vb`를 컴파일하고 `T2.exe` 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfee8-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfee8-123">참조</span><span class="sxs-lookup"><span data-stu-id="dfee8-123">See also</span></span>

- [<span data-ttu-id="dfee8-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="dfee8-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="dfee8-125">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfee8-125">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="dfee8-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="dfee8-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
