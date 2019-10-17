---
title: PrepForRemoting 메서드 (System)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405899"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="6bf00-102">PrepForRemoting 메서드</span><span class="sxs-lookup"><span data-stu-id="6bf00-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="6bf00-103">클라이언트 호출 사이트에서 예외가 다시 throw 되기 전에 서버 쪽 스택 추적을 메시지에 추가 하 여 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf00-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="6bf00-104">반환 값</span><span class="sxs-lookup"><span data-stu-id="6bf00-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="6bf00-105">이 <xref:System.Exception> 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf00-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bf00-106">주의</span><span class="sxs-lookup"><span data-stu-id="6bf00-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6bf00-107">@No__t-0 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf00-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6bf00-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf00-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6bf00-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bf00-109">Requirements</span></span>

<span data-ttu-id="6bf00-110">**네임스페이스:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="6bf00-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="6bf00-111">**어셈블리:** mscorlib.dll (mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="6bf00-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="6bf00-112">**.NET Framework 버전:** 1.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf00-112">**.NET Framework versions:** Available since 1.0.</span></span>
