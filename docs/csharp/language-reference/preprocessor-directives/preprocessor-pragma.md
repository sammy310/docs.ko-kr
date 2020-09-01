---
description: '#pragma - C# 참조'
title: '#pragma - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 97d7a786c83a8be21f7fd38873061dba0f9278ae
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137957"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="24a09-103">#pragma(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="24a09-103">#pragma (C# Reference)</span></span>
<span data-ttu-id="24a09-104">`#pragma`는 이 코드가 표시되는 파일의 컴파일에 대한 특수 명령을 컴파일러에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="24a09-105">컴파일러에서 명령을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="24a09-106">즉, `#pragma`를 사용하여 사용자 지정 전처리 명령을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="24a09-107">Microsoft C# 컴파일러는 다음 두 가지 `#pragma` 명령을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="24a09-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="24a09-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="24a09-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="24a09-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="24a09-110">구문</span><span class="sxs-lookup"><span data-stu-id="24a09-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="24a09-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24a09-111">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="24a09-112">인식된 pragma의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="24a09-113">pragma 관련 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="24a09-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a09-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24a09-114">See also</span></span>

- [<span data-ttu-id="24a09-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="24a09-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="24a09-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="24a09-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="24a09-117">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="24a09-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="24a09-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="24a09-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="24a09-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="24a09-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
