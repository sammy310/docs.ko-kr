---
description: 다음에 대해 자세히 알아보세요. WebHeaderCollection. AddInternal 메서드
title: WebHeaderCollection. AddInternal 메서드 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7bc84f84e6656dba5230b627fe9decfc4e0b4746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699482"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="a29cd-103">WebHeaderCollection. AddInternal 메서드</span><span class="sxs-lookup"><span data-stu-id="a29cd-103">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="a29cd-104">검사를 무시 하 고 컬렉션에 지정 된 이름과 값을 가진 새 헤더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a29cd-104">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="a29cd-105">이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29cd-105">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a29cd-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a29cd-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="a29cd-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a29cd-107">Parameters</span></span>

- <span data-ttu-id="a29cd-108">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a29cd-108">`name` <xref:System.String></span></span>

  <span data-ttu-id="a29cd-109">헤더의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a29cd-109">The name of the header.</span></span>

- <span data-ttu-id="a29cd-110">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a29cd-110">`value` <xref:System.String></span></span>

  <span data-ttu-id="a29cd-111">헤더의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a29cd-111">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="a29cd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a29cd-112">Requirements</span></span>

<span data-ttu-id="a29cd-113">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a29cd-113">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a29cd-114">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a29cd-114">**Assembly:** System (in System.dll)</span></span>
