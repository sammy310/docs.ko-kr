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
ms.openlocfilehash: ac385880f8c13c23dffff67fc2a1ecc5609fd189
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581411"
---
# <a name="-optioncompare"></a><span data-ttu-id="440a3-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="440a3-102">-optioncompare</span></span>

<span data-ttu-id="440a3-103">문자열 비교 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="440a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="440a3-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="440a3-105">설명</span><span class="sxs-lookup"><span data-stu-id="440a3-105">Remarks</span></span>

<span data-ttu-id="440a3-106">`-optioncompare`를 두 가지 형식 중 하나로 지정할 수 있습니다. 이진 문자열 비교를 사용하려면 `-optioncompare:binary`를 지정하고 텍스트 문자열 비교를 사용하려면 `-optioncompare:text`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="440a3-107">기본적으로 컴파일러는 `-optioncompare:binary`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="440a3-108">Microsoft Windows에서 현재 코드 페이지는 이진 정렬 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="440a3-109">일반적인 이진 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="440a3-110">텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정되는 대/소문자 미구분 텍스트 정렬 순서를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="440a3-111">일반적인 텍스트 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="440a3-112">Visual Studio IDE에서 -optioncompare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="440a3-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="440a3-113">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="440a3-114">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="440a3-115">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="440a3-116">**Option Compare** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="440a3-117">프로그래밍 방식으로 -optioncompare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="440a3-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="440a3-118">[Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="440a3-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="440a3-119">예제</span><span class="sxs-lookup"><span data-stu-id="440a3-119">Example</span></span>

<span data-ttu-id="440a3-120">다음 코드는 `ProjFile.vb`를 컴파일하고 이진 문자열 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="440a3-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="440a3-121">참조</span><span class="sxs-lookup"><span data-stu-id="440a3-121">See also</span></span>

- [<span data-ttu-id="440a3-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="440a3-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="440a3-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="440a3-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="440a3-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="440a3-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="440a3-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="440a3-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="440a3-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="440a3-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="440a3-127">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="440a3-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="440a3-128">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="440a3-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
