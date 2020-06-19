---
title: HttpStatusDescription 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990477"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="184ec-102">HttpStatusDescription 클래스</span><span class="sxs-lookup"><span data-stu-id="184ec-102">HttpStatusDescription class</span></span>

<span data-ttu-id="184ec-103">표준 HTTP 상태 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="184ec-104">이 클래스는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="184ec-105">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="184ec-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="184ec-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="184ec-107">Get method</span></span>

<span data-ttu-id="184ec-108">지정 된 HTTP 상태 코드와 연결 된 설명을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="184ec-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="184ec-109">Parameters</span></span>

<span data-ttu-id="184ec-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="184ec-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="184ec-111">HTTP 상태 코드입니다 (예:) `404` .</span><span class="sxs-lookup"><span data-stu-id="184ec-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="184ec-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="184ec-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="184ec-113">HTTP 상태 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="184ec-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="184ec-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="184ec-114">Requirements</span></span>

<span data-ttu-id="184ec-115">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="184ec-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="184ec-116">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="184ec-116">**Assembly:** System (in System.dll)</span></span>
