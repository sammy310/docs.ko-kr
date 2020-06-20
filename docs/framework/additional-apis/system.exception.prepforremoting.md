---
title: PrepForRemoting 메서드 (System)
description: .NET에서 PrepForRemoting 메서드를 검토 합니다. 메서드는 클라이언트에서 예외가 다시 throw 되기 전에 서버 쪽 스택 추적을 메시지에 추가 합니다.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105258"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="b63ba-104">Exception.PrepForRemoting 메서드</span><span class="sxs-lookup"><span data-stu-id="b63ba-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="b63ba-105">클라이언트 호출 사이트에서 예외가 다시 throw 되기 전에 서버 쪽 스택 추적을 메시지에 추가 하 여 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b63ba-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="b63ba-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="b63ba-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="b63ba-107">이 <xref:System.Exception> 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b63ba-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b63ba-108">설명</span><span class="sxs-lookup"><span data-stu-id="b63ba-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b63ba-109">`Exception.PrepForRemoting`메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ba-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b63ba-110">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ba-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b63ba-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b63ba-111">Requirements</span></span>

<span data-ttu-id="b63ba-112">**네임스페이스:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="b63ba-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="b63ba-113">**어셈블리:** mscorlib.dll (mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="b63ba-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="b63ba-114">**.NET Framework 버전:** 1.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b63ba-114">**.NET Framework versions:** Available since 1.0.</span></span>
