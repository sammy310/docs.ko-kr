---
description: -win32icon(C# 컴파일러 옵션)
title: -win32icon(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 5b62bbfe28bb5aa82605a88a83cf82eff9278807
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168870"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="f8b0e-103">-win32icon(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f8b0e-103">-win32icon (C# Compiler Options)</span></span>

<span data-ttu-id="f8b0e-104">**-win32icon** 옵션은 .ico 파일을 출력 파일에 삽입하여 파일 탐색기에서 출력 파일을 원하는 모양으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b0e-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8b0e-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8b0e-106">인수</span><span class="sxs-lookup"><span data-stu-id="f8b0e-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="f8b0e-107">출력 파일에 추가하려는 .ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8b0e-108">설명</span><span class="sxs-lookup"><span data-stu-id="f8b0e-108">Remarks</span></span>  

 <span data-ttu-id="f8b0e-109">.ico 파일은 [리소스 컴파일러](/windows/desktop/menurc/resource-compiler)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="f8b0e-110">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .iso 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="f8b0e-111">.NET Framework 리소스 파일을(참조하려면) [-linkresource](./linkresource-compiler-option.md)를(첨부하려면) [-resource](./resource-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="f8b0e-112">.res 파일을 가져오려면 [-win32res](./win32res-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f8b0e-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f8b0e-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f8b0e-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="f8b0e-115">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="f8b0e-116">**애플리케이션 아이콘** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="f8b0e-117">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b0e-118">예제</span><span class="sxs-lookup"><span data-stu-id="f8b0e-118">Example</span></span>  

 <span data-ttu-id="f8b0e-119">`in.cs`를 컴파일하고 .ico 파일 `rf.ico`를 첨부하여 `in.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0e-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8b0e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8b0e-120">See also</span></span>

- [<span data-ttu-id="f8b0e-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f8b0e-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f8b0e-122">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f8b0e-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
