---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004636"
---
# <a name="-win32icon"></a><span data-ttu-id="4c78e-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="4c78e-102">-win32icon</span></span>
<span data-ttu-id="4c78e-103">.Ico 파일을 출력 파일에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="4c78e-104">이 .ico 파일은 **파일 탐색기**에서 출력 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c78e-105">구문</span><span class="sxs-lookup"><span data-stu-id="4c78e-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c78e-106">인수</span><span class="sxs-lookup"><span data-stu-id="4c78e-106">Arguments</span></span>  
  
|<span data-ttu-id="4c78e-107">용어</span><span class="sxs-lookup"><span data-stu-id="4c78e-107">Term</span></span>|<span data-ttu-id="4c78e-108">정의</span><span class="sxs-lookup"><span data-stu-id="4c78e-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="4c78e-109">출력 파일에 추가할 .ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="4c78e-110">공백을 포함 하는 경우 파일 이름을 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c78e-111">설명</span><span class="sxs-lookup"><span data-stu-id="4c78e-111">Remarks</span></span>  
 <span data-ttu-id="4c78e-112">Microsoft Windows 리소스 컴파일러 (RC)를 사용 하 여 .ico 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="4c78e-113">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 호출 됩니다. .ico 파일은 .rc 파일에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="4c78e-114">@No__t-0 및 `-win32resource` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="4c78e-115">.NET Framework 리소스 파일을 첨부 하려면- [linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 을 참조 하 여 .NET Framework 리소스 파일 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c78e-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="4c78e-116">.Res 파일을 가져오려면 [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c78e-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="4c78e-117">Visual Studio IDE에서 win32icon로 설정</span><span class="sxs-lookup"><span data-stu-id="4c78e-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="4c78e-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4c78e-119">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4c78e-120">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="4c78e-121">3.  **아이콘** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c78e-122">예제</span><span class="sxs-lookup"><span data-stu-id="4c78e-122">Example</span></span>  
 <span data-ttu-id="4c78e-123">다음 코드는-0 @no__t 컴파일하고 .ico 파일 (`Rf.ico`)을 첨부 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c78e-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c78e-124">참조</span><span class="sxs-lookup"><span data-stu-id="4c78e-124">See also</span></span>

- [<span data-ttu-id="4c78e-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4c78e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4c78e-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4c78e-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
