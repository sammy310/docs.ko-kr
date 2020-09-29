---
description: '#pragma - C# 참조'
title: '#pragma - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168519"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="24553-103">#pragma(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="24553-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="24553-104">`#pragma`는 이 코드가 표시되는 파일의 컴파일에 대한 특수 명령을 컴파일러에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24553-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="24553-105">컴파일러에서 명령을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24553-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="24553-106">즉, `#pragma`를 사용하여 사용자 지정 전처리 명령을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24553-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="24553-107">Microsoft C# 컴파일러는 다음 두 가지 `#pragma` 명령을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="24553-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="24553-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="24553-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="24553-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="24553-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="24553-110">구문</span><span class="sxs-lookup"><span data-stu-id="24553-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="24553-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24553-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="24553-112">인식된 pragma의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24553-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="24553-113">pragma 관련 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="24553-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24553-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24553-114">See also</span></span>

- [<span data-ttu-id="24553-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="24553-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="24553-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="24553-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="24553-117">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="24553-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="24553-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="24553-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="24553-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="24553-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
