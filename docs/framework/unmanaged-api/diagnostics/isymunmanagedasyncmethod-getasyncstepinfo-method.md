---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: 5d3ee0d42773b70c8301260e5b4d6af1c7ceb938
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139862"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="d7a39-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a39-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="d7a39-103">[DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a39-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a39-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7a39-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7a39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7a39-105">Parameters</span></span>  
  
|<span data-ttu-id="d7a39-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7a39-106">Parameter</span></span>|<span data-ttu-id="d7a39-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7a39-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d7a39-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d7a39-108">Return Value</span></span>  
 <span data-ttu-id="d7a39-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a39-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a39-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a39-110">Requirements</span></span>  
 <span data-ttu-id="d7a39-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d7a39-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a39-112">참조</span><span class="sxs-lookup"><span data-stu-id="d7a39-112">See also</span></span>

- [<span data-ttu-id="d7a39-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a39-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
