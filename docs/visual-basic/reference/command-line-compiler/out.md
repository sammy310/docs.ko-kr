---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352383"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="5a81d-102">-out(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a81d-102">-out (Visual Basic)</span></span>
<span data-ttu-id="5a81d-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a81d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a81d-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a81d-105">인수</span><span class="sxs-lookup"><span data-stu-id="5a81d-105">Arguments</span></span>  
  
|<span data-ttu-id="5a81d-106">용어</span><span class="sxs-lookup"><span data-stu-id="5a81d-106">Term</span></span>|<span data-ttu-id="5a81d-107">정의</span><span class="sxs-lookup"><span data-stu-id="5a81d-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="5a81d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5a81d-108">Required.</span></span> <span data-ttu-id="5a81d-109">컴파일러에서 생성하는 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="5a81d-110">파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a81d-111">설명</span><span class="sxs-lookup"><span data-stu-id="5a81d-111">Remarks</span></span>  
 <span data-ttu-id="5a81d-112">생성할 파일의 전체 이름과 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="5a81d-113">이렇게 하지 않으면 .exe 파일은 `Sub Main` 프로시저를 포함하는 소스 코드 파일에서 해당 이름을 가져오고 .dll 파일은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="5a81d-114">.exe 또는 .dll 확장명 없이 파일 이름을 지정하면 `-target` 컴파일러 옵션에 지정된 값에 따라 컴파일러에서 자동으로 확장명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="5a81d-115">Visual Studio 통합 개발 환경에서 -out을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5a81d-116">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5a81d-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5a81d-118">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="5a81d-119">3.  **어셈블리 이름** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a81d-120">예제</span><span class="sxs-lookup"><span data-stu-id="5a81d-120">Example</span></span>  
 <span data-ttu-id="5a81d-121">다음 코드는 `T2.vb`를 컴파일하고 `T2.exe` 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a81d-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a81d-122">참조</span><span class="sxs-lookup"><span data-stu-id="5a81d-122">See also</span></span>

- [<span data-ttu-id="5a81d-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="5a81d-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5a81d-124">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a81d-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="5a81d-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="5a81d-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
