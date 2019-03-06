---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34792ddc7d32c89f6572a48e4636a63881611b88
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473554"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="7dae1-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="7dae1-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="7dae1-103">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7dae1-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dae1-104">구문</span><span class="sxs-lookup"><span data-stu-id="7dae1-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dae1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dae1-105">Parameters</span></span>  
  
|<span data-ttu-id="7dae1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dae1-106">Parameter</span></span>|<span data-ttu-id="7dae1-107">설명</span><span class="sxs-lookup"><span data-stu-id="7dae1-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="7dae1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7dae1-108">Return Value</span></span>  
 <span data-ttu-id="7dae1-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7dae1-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dae1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7dae1-110">Requirements</span></span>  
 <span data-ttu-id="7dae1-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7dae1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dae1-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7dae1-112">See also</span></span>
- [<span data-ttu-id="7dae1-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7dae1-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
