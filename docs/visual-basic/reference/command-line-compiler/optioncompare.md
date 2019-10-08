---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ee130073b95dfbab5616a54c188b09fa92ccc930
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005355"
---
# <a name="-optioncompare"></a><span data-ttu-id="923d6-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="923d6-102">-optioncompare</span></span>
<span data-ttu-id="923d6-103">문자열 비교 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="923d6-104">Syntax</span></span>  
  
```console  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="923d6-105">설명</span><span class="sxs-lookup"><span data-stu-id="923d6-105">Remarks</span></span>  
 <span data-ttu-id="923d6-106">두 가지 형식 중 하나에 `-optioncompare`을 지정할 수 있습니다. @no__t는 이진 문자열 비교를 사용 하 고, `-optioncompare:text`는 텍스트 문자열 비교를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="923d6-107">기본적으로 컴파일러는 `-optioncompare:binary`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="923d6-108">Microsoft Windows에서 현재 코드 페이지는 이진 정렬 순서를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="923d6-109">일반적인 이진 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="923d6-110">텍스트 기반 문자열 비교는 시스템의 로캘에서 결정 되는 대/소문자를 구분 하지 않는 텍스트 정렬 순서를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="923d6-111">일반적인 텍스트 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="923d6-112">Visual Studio IDE에서-기능 비교를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="923d6-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="923d6-113">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="923d6-114">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-114">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="923d6-115">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-115">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="923d6-116">**옵션 비교** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="923d6-117">프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="923d6-117">To set -optioncompare programmatically</span></span>  
  
- <span data-ttu-id="923d6-118">[Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="923d6-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="923d6-119">예제</span><span class="sxs-lookup"><span data-stu-id="923d6-119">Example</span></span>  
 <span data-ttu-id="923d6-120">다음 코드는-0 @no__t 컴파일하고 이진 문자열 비교를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="923d6-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="923d6-121">참조</span><span class="sxs-lookup"><span data-stu-id="923d6-121">See also</span></span>

- [<span data-ttu-id="923d6-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="923d6-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="923d6-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="923d6-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="923d6-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="923d6-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="923d6-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="923d6-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="923d6-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="923d6-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="923d6-127">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="923d6-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="923d6-128">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="923d6-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
