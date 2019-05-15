---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: dc48a8f79aa04892c514917da00b8fd6489695b1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593090"
---
# <a name="-win32icon"></a><span data-ttu-id="5e96b-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="5e96b-102">-win32icon</span></span>
<span data-ttu-id="5e96b-103">출력 파일에.ico 파일을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="5e96b-104">이.ico 파일에 출력 파일을 나타내는 **파일 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e96b-105">구문</span><span class="sxs-lookup"><span data-stu-id="5e96b-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="5e96b-106">인수</span><span class="sxs-lookup"><span data-stu-id="5e96b-106">Arguments</span></span>  
  
|<span data-ttu-id="5e96b-107">용어</span><span class="sxs-lookup"><span data-stu-id="5e96b-107">Term</span></span>|<span data-ttu-id="5e96b-108">정의</span><span class="sxs-lookup"><span data-stu-id="5e96b-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="5e96b-109">출력 파일에 추가할.ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="5e96b-110">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5e96b-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e96b-111">설명</span><span class="sxs-lookup"><span data-stu-id="5e96b-111">Remarks</span></span>  
 <span data-ttu-id="5e96b-112">Microsoft Windows 리소스 컴파일러 (RC) 사용 하 여.ico 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="5e96b-113">리소스 컴파일러를 호출 하는 시각적 개체를 컴파일할 때 C++ 프로그램; .ico 파일은.rc 파일에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="5e96b-114">합니다 `-win32icon` 고 `-win32resource` 옵션은 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="5e96b-115">참조 [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .NET Framework 리소스 파일을 참조 하 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework 리소스 파일을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="5e96b-116">참조 [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .res 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="5e96b-117">설정-Visual Studio IDE에서 win32icon</span><span class="sxs-lookup"><span data-stu-id="5e96b-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="5e96b-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5e96b-119">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5e96b-120">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="5e96b-121">3.  값을 수정 합니다 **아이콘** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5e96b-122">예제</span><span class="sxs-lookup"><span data-stu-id="5e96b-122">Example</span></span>  
 <span data-ttu-id="5e96b-123">다음 코드 컴파일을 `In.vb` .ico 파일을 연결 하 고 `Rf.ico`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e96b-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e96b-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e96b-124">See also</span></span>

- [<span data-ttu-id="5e96b-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="5e96b-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5e96b-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="5e96b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
