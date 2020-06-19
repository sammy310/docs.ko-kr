---
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
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990462"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="6e4b7-102">WebHeaderCollection. AddInternal 메서드</span><span class="sxs-lookup"><span data-stu-id="6e4b7-102">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="6e4b7-103">검사를 무시 하 고 컬렉션에 지정 된 이름과 값을 가진 새 헤더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-103">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="6e4b7-104">이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6e4b7-105">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="6e4b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e4b7-106">Parameters</span></span>

- <span data-ttu-id="6e4b7-107">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="6e4b7-107">`name` <xref:System.String></span></span>

  <span data-ttu-id="6e4b7-108">헤더의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-108">The name of the header.</span></span>

- <span data-ttu-id="6e4b7-109">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="6e4b7-109">`value` <xref:System.String></span></span>

  <span data-ttu-id="6e4b7-110">헤더의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e4b7-110">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e4b7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e4b7-111">Requirements</span></span>

<span data-ttu-id="6e4b7-112">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6e4b7-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6e4b7-113">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="6e4b7-113">**Assembly:** System (in System.dll)</span></span>
