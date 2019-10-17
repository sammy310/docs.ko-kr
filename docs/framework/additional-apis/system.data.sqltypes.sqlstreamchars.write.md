---
title: SqlStreamChars. Write (Char [], Int32, Int32) 메서드 (SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395581"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="5d2d2-102">SqlStreamChars. Write (Char [], Int32, Int32) 메서드</span><span class="sxs-lookup"><span data-stu-id="5d2d2-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="5d2d2-103">파생 클래스에서 재정의 되는 경우 현재 스트림에 문자 시퀀스를 쓰고 쓴 문자 수 만큼이 스트림 내의 현재 위치를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="5d2d2-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess .dll과의 friend 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5d2d2-105">SQL Server에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5d2d2-106">다른 데이터베이스의 경우 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="5d2d2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d2d2-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="5d2d2-108">쓸 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="5d2d2-109">원점을 기준으로 하는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="5d2d2-110">현재 스트림에 쓸 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d2d2-111">주의</span><span class="sxs-lookup"><span data-stu-id="5d2d2-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5d2d2-112">@No__t-0 메서드는 private 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5d2d2-113">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법 작성을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d2d2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d2d2-114">Requirements</span></span>

<span data-ttu-id="5d2d2-115">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5d2d2-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5d2d2-116">**어셈블리:** System.object (system.string)입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5d2d2-117">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2d2-117">**.NET Framework versions:** Available since 2.0.</span></span>
