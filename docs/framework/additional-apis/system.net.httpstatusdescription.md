---
description: '자세한 정보: HttpStatusDescription 클래스'
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
ms.openlocfilehash: fa135a6421397ce6b7be2af05d66aa8e81beafb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802504"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="b4f48-103">HttpStatusDescription 클래스</span><span class="sxs-lookup"><span data-stu-id="b4f48-103">HttpStatusDescription class</span></span>

<span data-ttu-id="b4f48-104">표준 HTTP 상태 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-104">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="b4f48-105">이 클래스는 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-105">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="b4f48-106">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b4f48-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="b4f48-108">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="b4f48-108">Get method</span></span>

<span data-ttu-id="b4f48-109">지정 된 HTTP 상태 코드와 연결 된 설명을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-109">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="b4f48-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4f48-110">Parameters</span></span>

<span data-ttu-id="b4f48-111">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="b4f48-111">`code` <xref:System.Int32></span></span>

<span data-ttu-id="b4f48-112">HTTP 상태 코드입니다 (예:) `404` .</span><span class="sxs-lookup"><span data-stu-id="b4f48-112">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="b4f48-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="b4f48-113">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="b4f48-114">HTTP 상태 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f48-114">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4f48-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4f48-115">Requirements</span></span>

<span data-ttu-id="b4f48-116">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b4f48-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b4f48-117">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="b4f48-117">**Assembly:** System (in System.dll)</span></span>
