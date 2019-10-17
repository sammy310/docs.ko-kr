---
title: SqlStreamChars. Close 메서드 (SqlTypes)
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
ms.openlocfilehash: c33c60842d181be7011528ca7550f3d09f291f43
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395629"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="45608-102">SqlStreamChars. Close 메서드</span><span class="sxs-lookup"><span data-stu-id="45608-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="45608-103">현재 스트림을 닫고 스트림과 연결 된 시스템 리소스를 모두 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="45608-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="45608-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess .dll과의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45608-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="45608-105">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45608-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="45608-106"> 다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45608-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="45608-107">주의</span><span class="sxs-lookup"><span data-stu-id="45608-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="45608-108">@No__t-0 메서드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45608-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="45608-109">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45608-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="45608-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45608-110">Requirements</span></span>

<span data-ttu-id="45608-111">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="45608-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="45608-112">**어셈블리:** System.object (system.string)입니다.</span><span class="sxs-lookup"><span data-stu-id="45608-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="45608-113">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45608-113">**.NET Framework versions:** Available since 2.0.</span></span>
