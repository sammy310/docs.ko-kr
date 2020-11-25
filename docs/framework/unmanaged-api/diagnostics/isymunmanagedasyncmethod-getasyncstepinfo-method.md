---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: f9392dae4119e59b4eb0fdb87e2b334b32b77109
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707258"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="327e6-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="327e6-103">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="327e6-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="327e6-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="327e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="327e6-105">Parameters</span></span>  
  
|<span data-ttu-id="327e6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="327e6-106">Parameter</span></span>|<span data-ttu-id="327e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="327e6-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="327e6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="327e6-108">Return Value</span></span>  

 <span data-ttu-id="327e6-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="327e6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="327e6-110">Requirements</span></span>  

 <span data-ttu-id="327e6-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="327e6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327e6-112">참조</span><span class="sxs-lookup"><span data-stu-id="327e6-112">See also</span></span>

- [<span data-ttu-id="327e6-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="327e6-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
