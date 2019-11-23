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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352383"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="96f3a-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96f3a-102">-out (Visual Basic)</span></span>
<span data-ttu-id="96f3a-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96f3a-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="96f3a-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="96f3a-105">인수</span><span class="sxs-lookup"><span data-stu-id="96f3a-105">Arguments</span></span>  
  
|<span data-ttu-id="96f3a-106">용어</span><span class="sxs-lookup"><span data-stu-id="96f3a-106">Term</span></span>|<span data-ttu-id="96f3a-107">정의</span><span class="sxs-lookup"><span data-stu-id="96f3a-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="96f3a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="96f3a-108">Required.</span></span> <span data-ttu-id="96f3a-109">The name of the output file the compiler creates.</span><span class="sxs-lookup"><span data-stu-id="96f3a-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="96f3a-110">If the file name contains a space, enclose the name in quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="96f3a-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f3a-111">주의</span><span class="sxs-lookup"><span data-stu-id="96f3a-111">Remarks</span></span>  
 <span data-ttu-id="96f3a-112">Specify the full name and extension of the file to create.</span><span class="sxs-lookup"><span data-stu-id="96f3a-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="96f3a-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span><span class="sxs-lookup"><span data-stu-id="96f3a-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="96f3a-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span><span class="sxs-lookup"><span data-stu-id="96f3a-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="96f3a-115">To set -out in the Visual Studio integrated development environment</span><span class="sxs-lookup"><span data-stu-id="96f3a-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="96f3a-116">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="96f3a-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="96f3a-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96f3a-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="96f3a-118">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96f3a-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="96f3a-119">3.  Modify the value in the **Assembly Name** box.</span><span class="sxs-lookup"><span data-stu-id="96f3a-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96f3a-120">예제</span><span class="sxs-lookup"><span data-stu-id="96f3a-120">Example</span></span>  
 <span data-ttu-id="96f3a-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="96f3a-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="96f3a-122">참조</span><span class="sxs-lookup"><span data-stu-id="96f3a-122">See also</span></span>

- [<span data-ttu-id="96f3a-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="96f3a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="96f3a-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96f3a-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="96f3a-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="96f3a-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
