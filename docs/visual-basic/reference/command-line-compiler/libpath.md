---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716633"
---
# <a name="-libpath"></a><span data-ttu-id="26a93-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="26a93-102">-libpath</span></span>
<span data-ttu-id="26a93-103">참조된 어셈블리의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a93-104">구문</span><span class="sxs-lookup"><span data-stu-id="26a93-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="26a93-105">인수</span><span class="sxs-lookup"><span data-stu-id="26a93-105">Arguments</span></span>  
  
|<span data-ttu-id="26a93-106">용어</span><span class="sxs-lookup"><span data-stu-id="26a93-106">Term</span></span>|<span data-ttu-id="26a93-107">정의</span><span class="sxs-lookup"><span data-stu-id="26a93-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="26a93-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="26a93-108">Required.</span></span> <span data-ttu-id="26a93-109">참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 세미콜론으로 구분된 디렉터리 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="26a93-110">디렉터리 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26a93-111">설명</span><span class="sxs-lookup"><span data-stu-id="26a93-111">Remarks</span></span>  
 <span data-ttu-id="26a93-112">`-libpath` 옵션은 [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션에서 참조하는 어셈블리의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="26a93-113">컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="26a93-114">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-114">Current working directory.</span></span> <span data-ttu-id="26a93-115">컴파일러가 호출되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="26a93-116">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="26a93-117">`-libpath`로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="26a93-118">LIB 환경 변수로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="26a93-119">`-libpath` 옵션은 가감되므로 두 번 이상 지정하면 이전 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="26a93-120">`-reference`를 사용하여 어셈블리 참조를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="26a93-121">Visual Studio 통합 개발 환경에서 -libpath를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="26a93-122">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="26a93-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="26a93-124">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="26a93-125">3.  **참조 경로...** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="26a93-126">4.  **참조 경로** 대화 상자의 **Folder:** 상자에 디렉터리 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="26a93-127">5.  **폴더 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26a93-128">예제</span><span class="sxs-lookup"><span data-stu-id="26a93-128">Example</span></span>  
 <span data-ttu-id="26a93-129">다음 코드는 `T2.vb`를 컴파일하여 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="26a93-130">컴파일러는 작업 디렉터리, C: 드라이브의 루트 디렉터리 및 C: 드라이브의 새 어셈블리 디렉터리에서 어셈블리 참조를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="26a93-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="26a93-131">참조</span><span class="sxs-lookup"><span data-stu-id="26a93-131">See also</span></span>

- [<span data-ttu-id="26a93-132">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="26a93-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="26a93-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="26a93-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="26a93-134">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="26a93-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
