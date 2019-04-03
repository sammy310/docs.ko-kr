---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: b8e28b821f6536ddb5c7612e8706e024dd79a0bd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833319"
---
# <a name="-libpath"></a><span data-ttu-id="d8b27-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="d8b27-102">-libpath</span></span>
<span data-ttu-id="d8b27-103">참조 된 어셈블리의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b27-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8b27-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8b27-105">인수</span><span class="sxs-lookup"><span data-stu-id="d8b27-105">Arguments</span></span>  
  
|<span data-ttu-id="d8b27-106">용어</span><span class="sxs-lookup"><span data-stu-id="d8b27-106">Term</span></span>|<span data-ttu-id="d8b27-107">정의</span><span class="sxs-lookup"><span data-stu-id="d8b27-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="d8b27-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d8b27-108">Required.</span></span> <span data-ttu-id="d8b27-109">컴파일러가 참조 된 어셈블리에서에서 찾는 대 한 디렉터리의 세미콜론으로 구분 된 목록에 없는 하나는 현재 작업 디렉터리 (컴파일러를 호출 하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="d8b27-110">디렉터리 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="d8b27-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b27-111">설명</span><span class="sxs-lookup"><span data-stu-id="d8b27-111">Remarks</span></span>  
 <span data-ttu-id="d8b27-112">합니다 `-libpath` 옵션에서 참조 어셈블리의 위치를 지정 합니다 [-참조](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="d8b27-113">컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="d8b27-114">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-114">Current working directory.</span></span> <span data-ttu-id="d8b27-115">컴파일러가 호출되는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="d8b27-116">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="d8b27-117">지정 된 디렉터리 `/libpath`합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="d8b27-118">LIB 환경 변수로 지정된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="d8b27-119">`-libpath` 가산적; 지정 옵션은 이전 값에 추가 되 면 보다 더 많은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="d8b27-120">사용 하 여 `-reference` 어셈블리 참조를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="d8b27-121">Visual Studio에서 /libpath를 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="d8b27-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d8b27-122">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d8b27-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d8b27-124">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="d8b27-125">3.  클릭 된 **경로 참조 하는 중...**  단추입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="d8b27-126">4.  에 **참조 경로** 대화 상자에서 디렉터리 이름을 입력 합니다 합니다 **폴더:** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="d8b27-127">5.  클릭 **폴더 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8b27-128">예제</span><span class="sxs-lookup"><span data-stu-id="d8b27-128">Example</span></span>  
 <span data-ttu-id="d8b27-129">다음 코드에서는 `T2.vb` .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="d8b27-130">컴파일러는 어셈블리 참조에 대 한 작업 디렉터리, c: 드라이브의 루트 디렉터리 및 c: 드라이브의 새 어셈블리 디렉터리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8b27-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="d8b27-131">See also</span></span>

- [<span data-ttu-id="d8b27-132">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d8b27-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="d8b27-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d8b27-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d8b27-134">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d8b27-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
