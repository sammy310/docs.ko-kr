---
title: '#pragma - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712457"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3bf75-102">#pragma(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3bf75-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="3bf75-103">`#pragma`는 이 코드가 표시되는 파일의 컴파일에 대한 특수 명령을 컴파일러에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3bf75-104">컴파일러에서 명령을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3bf75-105">즉, `#pragma`를 사용하여 사용자 지정 전처리 명령을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3bf75-106">Microsoft C# 컴파일러는 다음 두 가지 `#pragma` 명령을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3bf75-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3bf75-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3bf75-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3bf75-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3bf75-109">구문</span><span class="sxs-lookup"><span data-stu-id="3bf75-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bf75-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bf75-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="3bf75-111">인식된 pragma의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3bf75-112">pragma 관련 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="3bf75-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf75-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bf75-113">See also</span></span>

- [<span data-ttu-id="3bf75-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3bf75-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3bf75-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3bf75-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3bf75-116">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="3bf75-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="3bf75-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3bf75-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="3bf75-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3bf75-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
