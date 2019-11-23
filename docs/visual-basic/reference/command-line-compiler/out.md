---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005336"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="46a06-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46a06-102">-out (Visual Basic)</span></span>
<span data-ttu-id="46a06-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a06-104">구문</span><span class="sxs-lookup"><span data-stu-id="46a06-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="46a06-105">인수</span><span class="sxs-lookup"><span data-stu-id="46a06-105">Arguments</span></span>  
  
|<span data-ttu-id="46a06-106">용어</span><span class="sxs-lookup"><span data-stu-id="46a06-106">Term</span></span>|<span data-ttu-id="46a06-107">정의</span><span class="sxs-lookup"><span data-stu-id="46a06-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="46a06-108">필수</span><span class="sxs-lookup"><span data-stu-id="46a06-108">Required.</span></span> <span data-ttu-id="46a06-109">컴파일러가 만드는 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="46a06-110">파일 이름에 공백이 포함 된 경우 이름을 큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46a06-111">주의</span><span class="sxs-lookup"><span data-stu-id="46a06-111">Remarks</span></span>  
 <span data-ttu-id="46a06-112">만들 파일의 전체 이름 및 확장명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="46a06-113">이렇게 하지 않으면 .exe 파일은 `Sub Main` 프로시저를 포함 하는 소스 코드 파일에서 해당 이름을 사용 하 고 .dll 파일은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="46a06-114">.Exe 또는 .dll 확장명 없이 파일 이름을 지정 하는 경우 컴파일러는 `-target` 컴파일러 옵션에 지정 된 값에 따라 자동으로 확장을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="46a06-115">Visual Studio 통합 개발 환경에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="46a06-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="46a06-116">1. **솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="46a06-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="46a06-118">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="46a06-119">3. **어셈블리 이름** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46a06-120">예제</span><span class="sxs-lookup"><span data-stu-id="46a06-120">Example</span></span>  
 <span data-ttu-id="46a06-121">다음 코드는 `T2.vb`를 컴파일하고 `T2.exe`출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46a06-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="46a06-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46a06-122">See also</span></span>

- [<span data-ttu-id="46a06-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="46a06-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="46a06-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46a06-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="46a06-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="46a06-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
