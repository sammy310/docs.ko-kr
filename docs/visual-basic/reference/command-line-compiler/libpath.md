---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005459"
---
# <a name="-libpath"></a><span data-ttu-id="357ab-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="357ab-102">-libpath</span></span>
<span data-ttu-id="357ab-103">참조 된 어셈블리의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="357ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="357ab-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="357ab-105">인수</span><span class="sxs-lookup"><span data-stu-id="357ab-105">Arguments</span></span>  
  
|<span data-ttu-id="357ab-106">용어</span><span class="sxs-lookup"><span data-stu-id="357ab-106">Term</span></span>|<span data-ttu-id="357ab-107">정의</span><span class="sxs-lookup"><span data-stu-id="357ab-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="357ab-108">필수.</span><span class="sxs-lookup"><span data-stu-id="357ab-108">Required.</span></span> <span data-ttu-id="357ab-109">컴파일러가 참조 된 어셈블리를 현재 작업 디렉터리 (컴파일러를 호출 하 고 있는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 조회할 세미콜론으로 구분 된 디렉터리 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="357ab-110">디렉터리 이름에 공백이 포함 된 경우 이름을 큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="357ab-111">설명</span><span class="sxs-lookup"><span data-stu-id="357ab-111">Remarks</span></span>  
 <span data-ttu-id="357ab-112">@No__t-0 옵션은 [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션에서 참조 하는 어셈블리의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="357ab-113">컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="357ab-114">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-114">Current working directory.</span></span> <span data-ttu-id="357ab-115">컴파일러가 호출되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="357ab-116">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="357ab-117">@No__t로 지정 된 디렉터리-0.</span><span class="sxs-lookup"><span data-stu-id="357ab-117">Directories specified by `/libpath`.</span></span>  
  
4. <span data-ttu-id="357ab-118">LIB 환경 변수로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="357ab-119">@No__t-0 옵션은 가감 연산자입니다. 두 번 이상 지정 하면 이전 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="357ab-120">@No__t-0을 사용 하 여 어셈블리 참조를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="357ab-121">Visual Studio 통합 개발 환경에서/libpath를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="357ab-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="357ab-122">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="357ab-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="357ab-124">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="357ab-125">3.  **참조 경로 ...** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="357ab-126">4.  **참조 경로** 대화 상자에서 **폴더:** 상자에 디렉터리 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="357ab-127">5.  **폴더 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="357ab-128">예제</span><span class="sxs-lookup"><span data-stu-id="357ab-128">Example</span></span>  
 <span data-ttu-id="357ab-129">다음 코드는 `T2.vb`을 컴파일하여 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="357ab-130">컴파일러는 C: 드라이브의 루트 디렉터리와 어셈블리 참조를 위한 C: 드라이브의 새 어셈블리 디렉터리에서 작업 디렉터리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="357ab-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="357ab-131">참조</span><span class="sxs-lookup"><span data-stu-id="357ab-131">See also</span></span>

- [<span data-ttu-id="357ab-132">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="357ab-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="357ab-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="357ab-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="357ab-134">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="357ab-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
