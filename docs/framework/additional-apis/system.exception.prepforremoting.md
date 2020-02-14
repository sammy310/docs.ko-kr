---
title: PrepForRemoting 메서드 (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214892"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="eeae9-102">Exception.PrepForRemoting 메서드</span><span class="sxs-lookup"><span data-stu-id="eeae9-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="eeae9-103">클라이언트 호출 사이트에서 예외가 다시 throw 되기 전에 서버 쪽 스택 추적을 메시지에 추가 하 여 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeae9-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="eeae9-104">반환</span><span class="sxs-lookup"><span data-stu-id="eeae9-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="eeae9-105">이 <xref:System.Exception> 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="eeae9-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="eeae9-106">설명</span><span class="sxs-lookup"><span data-stu-id="eeae9-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="eeae9-107">`Exception.PrepForRemoting` 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeae9-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="eeae9-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeae9-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="eeae9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eeae9-109">Requirements</span></span>

<span data-ttu-id="eeae9-110">**네임 스페이스:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="eeae9-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="eeae9-111">**어셈블리:** mscorlib.dll (mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="eeae9-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="eeae9-112">**.NET Framework 버전:** 1.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeae9-112">**.NET Framework versions:** Available since 1.0.</span></span>
