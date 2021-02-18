---
description: '자세한 정보: -optioncompare'
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
ms.openlocfilehash: 9be4867c75cc16a8f699cf492dc41e9d08b96495
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475931"
---
# <a name="-optioncompare"></a><span data-ttu-id="f096b-103">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="f096b-103">-optioncompare</span></span>

<span data-ttu-id="f096b-104">문자열 비교 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-104">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="f096b-105">구문</span><span class="sxs-lookup"><span data-stu-id="f096b-105">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="f096b-106">설명</span><span class="sxs-lookup"><span data-stu-id="f096b-106">Remarks</span></span>

<span data-ttu-id="f096b-107">`-optioncompare`를 두 가지 형식 중 하나로 지정할 수 있습니다. 이진 문자열 비교를 사용하려면 `-optioncompare:binary`를 지정하고 텍스트 문자열 비교를 사용하려면 `-optioncompare:text`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-107">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="f096b-108">기본적으로 컴파일러는 `-optioncompare:binary`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-108">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="f096b-109">Microsoft Windows에서 현재 코드 페이지는 이진 정렬 순서를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-109">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="f096b-110">일반적인 이진 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-110">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="f096b-111">텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정되는 대/소문자 미구분 텍스트 정렬 순서를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-111">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="f096b-112">일반적인 텍스트 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-112">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="f096b-113">Visual Studio IDE에서 -optioncompare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f096b-113">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="f096b-114">**솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f096b-115">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-115">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="f096b-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-116">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="f096b-117">**Option Compare** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-117">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="f096b-118">프로그래밍 방식으로 -optioncompare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f096b-118">To set -optioncompare programmatically</span></span>

<span data-ttu-id="f096b-119">[Option Compare 문](../../language-reference/statements/option-compare-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f096b-119">See [Option Compare Statement](../../language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="f096b-120">예제</span><span class="sxs-lookup"><span data-stu-id="f096b-120">Example</span></span>

<span data-ttu-id="f096b-121">다음 코드는 `ProjFile.vb`를 컴파일하고 이진 문자열 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f096b-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="f096b-122">참조</span><span class="sxs-lookup"><span data-stu-id="f096b-122">See also</span></span>

- [<span data-ttu-id="f096b-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="f096b-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f096b-124">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="f096b-124">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="f096b-125">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="f096b-125">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="f096b-126">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="f096b-126">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="f096b-127">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="f096b-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f096b-128">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="f096b-128">Option Compare Statement</span></span>](../../language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="f096b-129">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="f096b-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
