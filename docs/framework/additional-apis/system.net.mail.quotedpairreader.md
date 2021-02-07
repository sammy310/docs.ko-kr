---
description: '자세히 알아보기: QuotedPairReader 클래스'
title: QuotedPairReader 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 810a7b02948a1b7aa542a179563af9a6d79dd763
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699664"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="b3596-103">QuotedPairReader 클래스</span><span class="sxs-lookup"><span data-stu-id="b3596-103">QuotedPairReader class</span></span>

<span data-ttu-id="b3596-104">따옴표 붙은 문자열에서 따옴표로 묶인 (이스케이프 됨) 문자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-104">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="b3596-105">이 클래스는 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-105">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="b3596-106">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b3596-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="b3596-108">CountQuotedChars 메서드</span><span class="sxs-lookup"><span data-stu-id="b3596-108">CountQuotedChars method</span></span>

<span data-ttu-id="b3596-109">지정 된 문자열에서 따옴표 붙은 여러 개의 백슬래시를 포함 하 여 연속 된 따옴표 문자의 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-109">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="b3596-110">예를 들어 문자열 `a\\\b` 및의 인덱스가 제공 된 경우 `4` `4` `b` 는가 따옴표 붙은이 고 따라서 앞에 오는 백슬래시 세 개 이므로 메서드는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-110">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="b3596-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3596-111">Parameters</span></span>

- <span data-ttu-id="b3596-112">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="b3596-112">`data` <xref:System.String></span></span>

  <span data-ttu-id="b3596-113">연속 되는 따옴표 붙은 문자를 계산할 데이터 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-113">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="b3596-114">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="b3596-114">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="b3596-115">지정 된 문자열에서 최대 연속 따옴표 문자를 포함 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-115">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="b3596-116">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="b3596-116">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="b3596-117">`true` 유니코드 문자를 이스케이프 하도록 허용 하려면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-117">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="b3596-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3596-118">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="b3596-119">`0` 지정 된 인덱스에 있는 문자가 이스케이프 되지 않으면이 고, 그렇지 않으면입니다. 그렇지 않으면에서 문자를 포함 하 여 최대 연속 따옴표 안에 포함 된 문자 수입니다 `index` .</span><span class="sxs-lookup"><span data-stu-id="b3596-119">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b3596-120">예외</span><span class="sxs-lookup"><span data-stu-id="b3596-120">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="b3596-121">이스케이프 된 유니코드 문자를 찾았지만 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3596-121">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3596-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3596-122">Requirements</span></span>

<span data-ttu-id="b3596-123">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b3596-123">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b3596-124">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="b3596-124">**Assembly:** System (in System.dll)</span></span>
