---
title: SqlStreamChars.Close 메서드 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d0c29bbc5c6bea98cf36e3c2b6bf7825d6843ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705872"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="f163f-102">SqlStreamChars.Close 메서드</span><span class="sxs-lookup"><span data-stu-id="f163f-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="f163f-103">현재 스트림을 닫고 스트림과 연결 된 시스템 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="f163f-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f163f-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="f163f-106"> 다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="f163f-107">설명</span><span class="sxs-lookup"><span data-stu-id="f163f-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f163f-108">`SqlStreamChars.Close` 메서드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f163f-109">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f163f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f163f-110">Requirements</span></span>

<span data-ttu-id="f163f-111">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f163f-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f163f-112">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="f163f-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f163f-113">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f163f-113">**.NET Framework versions:** Available since 2.0.</span></span>