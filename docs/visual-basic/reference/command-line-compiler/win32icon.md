---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: c6d5e054063592db5777a76fe19da79337ed5034
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084959"
---
# <a name="-win32icon"></a><span data-ttu-id="372df-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="372df-102">-win32icon</span></span>

<span data-ttu-id="372df-103">출력 파일에 .ico 파일을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="372df-104">이 .ico 파일은 **파일 탐색기**에서 출력 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="372df-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372df-105">구문</span><span class="sxs-lookup"><span data-stu-id="372df-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="372df-106">인수</span><span class="sxs-lookup"><span data-stu-id="372df-106">Arguments</span></span>  
  
|<span data-ttu-id="372df-107">용어</span><span class="sxs-lookup"><span data-stu-id="372df-107">Term</span></span>|<span data-ttu-id="372df-108">정의</span><span class="sxs-lookup"><span data-stu-id="372df-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="372df-109">출력 파일에 추가할 .ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="372df-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="372df-110">공백이 있으면 파일 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="372df-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="372df-111">설명</span><span class="sxs-lookup"><span data-stu-id="372df-111">Remarks</span></span>  

 <span data-ttu-id="372df-112">Microsoft Windows RC(리소스 컴파일러)를 사용하여 .ico 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="372df-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="372df-113">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 호출됩니다. .iso 파일은 .rc 파일에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="372df-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="372df-114">`-win32icon` 및 `-win32resource` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="372df-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="372df-115">.NET Framework 리소스 파일 또는 [-resource (Visual Basic)](resource.md)를 참조하여 .NET Framework 리소스 파일을 연결하려면 [-linkresource(Visual Basic)](linkresource.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="372df-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="372df-116">.res 파일을 가져오려면 [-win32resource](win32resource.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="372df-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="372df-117">Visual Studio IDE에서 -win32icon을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="372df-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="372df-119">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="372df-120">2.  **애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="372df-121">3.  **아이콘** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="372df-122">예제</span><span class="sxs-lookup"><span data-stu-id="372df-122">Example</span></span>  

 <span data-ttu-id="372df-123">다음 코드에서는 `In.vb`를 컴파일하고 .ico 파일 `Rf.ico`를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="372df-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="372df-124">참조</span><span class="sxs-lookup"><span data-stu-id="372df-124">See also</span></span>

- [<span data-ttu-id="372df-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="372df-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="372df-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="372df-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
