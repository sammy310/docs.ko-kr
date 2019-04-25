---
title: SqlStreamChars.Read (Char, Int32, Int32) 메서드 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: df92acfd4050eb16d3a101b20b9b44560273f4d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675236"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="d6345-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span><span class="sxs-lookup"><span data-stu-id="d6345-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="d6345-103">파생된 클래스에서 재정의할 경우, 입력 스트림에서 다음 문자 집합을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="d6345-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d6345-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d6345-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="d6345-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6345-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="d6345-108">읽을 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="d6345-109">원점 기준으로 하는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="d6345-110">현재 스트림에서 읽을 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="d6345-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d6345-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="d6345-112">버퍼로 읽어온 총 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6345-113">설명</span><span class="sxs-lookup"><span data-stu-id="d6345-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d6345-114">`SqlStreamChars.Read` 메서드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d6345-115">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6345-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6345-116">Requirements</span></span>

<span data-ttu-id="d6345-117">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d6345-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d6345-118">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="d6345-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d6345-119">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6345-119">**.NET Framework versions:** Available since 2.0.</span></span>