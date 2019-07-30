---
title: 소스 줄, 파일 및 경로 식별자
description: 코드의 소스 줄 번호, 디렉터리 F# 및 파일 이름에 액세스할 수 있는 기본 제공 식별자 값을 사용 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5ff36210edc75370f8baf9ee7be057f3ac0c3979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627120"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="efbe6-103">소스 줄, 파일 및 경로 식별자</span><span class="sxs-lookup"><span data-stu-id="efbe6-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="efbe6-104">`__SOURCE_DIRECTORY__` 및 `__LINE__` 식별자는코드의소스줄번호,디렉터리및파일이름에액세스할수있는기본`__SOURCE_FILE__` 제공 값입니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="efbe6-105">구문</span><span class="sxs-lookup"><span data-stu-id="efbe6-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="efbe6-106">설명</span><span class="sxs-lookup"><span data-stu-id="efbe6-106">Remarks</span></span>

<span data-ttu-id="efbe6-107">이러한 각 값에는 형식이 `string`있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="efbe6-108">다음 표에서는에서 F#사용할 수 있는 소스 줄, 파일 및 경로 식별자를 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="efbe6-109">이러한 식별자는 전처리기 매크로가 아닙니다. 이러한 값은 컴파일러에서 인식 하는 기본 제공 값입니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="efbe6-110">미리 정의 된 식별자</span><span class="sxs-lookup"><span data-stu-id="efbe6-110">Predefined identifier</span></span>|<span data-ttu-id="efbe6-111">Description</span><span class="sxs-lookup"><span data-stu-id="efbe6-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="efbe6-112">지시문을 고려 `#line` 하 여 현재 줄 번호로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="efbe6-113">지시문을 고려 `#line` 하 여 원본 디렉터리의 현재 전체 경로를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="efbe6-114">는 지시문을 고려 `#line` 하 여 경로 없이 현재 소스 파일 이름으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="efbe6-115">`#line` 지시문에 대 한 자세한 내용은 [컴파일러 지시문](compiler-directives.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="efbe6-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="efbe6-116">예제</span><span class="sxs-lookup"><span data-stu-id="efbe6-116">Example</span></span>

<span data-ttu-id="efbe6-117">다음 코드 예제에서는 이러한 값을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efbe6-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="efbe6-118">출력:</span><span class="sxs-lookup"><span data-stu-id="efbe6-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="efbe6-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="efbe6-119">See also</span></span>

- [<span data-ttu-id="efbe6-120">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="efbe6-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="efbe6-121">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="efbe6-121">F# Language Reference</span></span>](index.md)
