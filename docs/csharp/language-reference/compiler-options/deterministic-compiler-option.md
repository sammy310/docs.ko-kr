---
description: -deterministic(C# 컴파일러 옵션)
title: -deterministic(C# 컴파일러 옵션)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: d64f4d4b0d4e9b5ed2cc1ee40662dc669fc6660d
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235328"
---
# <a name="-deterministic"></a><span data-ttu-id="48302-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="48302-103">-deterministic</span></span>

<span data-ttu-id="48302-104">컴파일러에서 동일한 입력에 대한 컴파일 간에 바이트 단위(byte-for-byte) 출력이 동일한 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="48302-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="48302-105">구문</span><span class="sxs-lookup"><span data-stu-id="48302-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="48302-106">설명</span><span class="sxs-lookup"><span data-stu-id="48302-106">Remarks</span></span>

<span data-ttu-id="48302-107">기본적으로 컴파일러에서 타임스탬프 및 난수에서 생성된 MVID를 추가하기 때문에 지정된 입력 세트의 컴파일러 출력은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="48302-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a MVID that is generated from random numbers.</span></span> <span data-ttu-id="48302-108">`-deterministic` 옵션을 사용하여 *결정적 어셈블리* 를 생성하고, 입력이 동일하게 유지되는 한 해당 이진 콘텐츠가 컴파일 간에 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="48302-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span> <span data-ttu-id="48302-109">해당 빌드에서 타임스탬프 및 MVID 필드는 모든 컴파일 입력의 해시에서 파생된 값으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="48302-109">In such a build, the timestamp and MVID fields will be replaced with values derived from a hash of all the compilation inputs.</span></span>

<span data-ttu-id="48302-110">결정성의 목적을 위해 컴파일러에서 고려하는 입력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48302-110">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="48302-111">명령줄 매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="48302-111">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="48302-112">컴파일러의 .rsp 지시 파일의 내용</span><span class="sxs-lookup"><span data-stu-id="48302-112">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="48302-113">사용된 컴파일러의 정확한 버전 및 참조되는 어셈블리</span><span class="sxs-lookup"><span data-stu-id="48302-113">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="48302-114">현재 디렉터리 경로</span><span class="sxs-lookup"><span data-stu-id="48302-114">The current directory path.</span></span>
- <span data-ttu-id="48302-115">다음을 포함하여 직접 또는 간접적으로 컴파일러에 명시적으로 전달된 모든 파일의 이진 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="48302-115">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="48302-116">소스 파일</span><span class="sxs-lookup"><span data-stu-id="48302-116">Source files</span></span>
  - <span data-ttu-id="48302-117">참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="48302-117">Referenced assemblies</span></span>
  - <span data-ttu-id="48302-118">참조된 모듈</span><span class="sxs-lookup"><span data-stu-id="48302-118">Referenced modules</span></span>
  - <span data-ttu-id="48302-119">리소스</span><span class="sxs-lookup"><span data-stu-id="48302-119">Resources</span></span>
  - <span data-ttu-id="48302-120">강력한 이름 키 파일</span><span class="sxs-lookup"><span data-stu-id="48302-120">The strong name key file</span></span>
  - <span data-ttu-id="48302-121">@ 지시 파일</span><span class="sxs-lookup"><span data-stu-id="48302-121">@ response files</span></span>
  - <span data-ttu-id="48302-122">분석기</span><span class="sxs-lookup"><span data-stu-id="48302-122">Analyzers</span></span>
  - <span data-ttu-id="48302-123">규칙 집합</span><span class="sxs-lookup"><span data-stu-id="48302-123">Rulesets</span></span>
  - <span data-ttu-id="48302-124">분석기에서 사용할 수 있는 추가 파일</span><span class="sxs-lookup"><span data-stu-id="48302-124">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="48302-125">현재 문화권(진단 및 예외 메시지가 생성되는 언어)</span><span class="sxs-lookup"><span data-stu-id="48302-125">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="48302-126">인코딩이 지정되지 않은 경우 기본 인코딩(또는 현재 코드 페이지)</span><span class="sxs-lookup"><span data-stu-id="48302-126">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="48302-127">컴파일러의 검색 경로(예: `-lib` 또는 `-recurse`로 지정)에 있는 파일의 존재 여부 및 내용</span><span class="sxs-lookup"><span data-stu-id="48302-127">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="48302-128">컴파일러가 실행되는 CLR 플랫폼</span><span class="sxs-lookup"><span data-stu-id="48302-128">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="48302-129">`%LIBPATH%` 값(분석기 종속성 로드에 영향을 줄 수 있음)</span><span class="sxs-lookup"><span data-stu-id="48302-129">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="48302-130">원본을 공개적으로 사용할 수 있는 경우 결정적 컴파일을 사용하여 이진 파일이 신뢰할 수 있는 원본에서 컴파일되는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48302-130">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="48302-131">또한 연속 빌드 시스템에서 이진 파일 변경에 종속된 빌드 단계를 실행해야 하는지 여부를 확인하는 데 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48302-131">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="48302-132">참조</span><span class="sxs-lookup"><span data-stu-id="48302-132">See also</span></span>

- [<span data-ttu-id="48302-133">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="48302-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="48302-134">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="48302-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
