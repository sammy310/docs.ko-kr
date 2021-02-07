---
description: '자세히 알아보기: ISymUnmanagedAsyncMethod:: GetAsyncStepInfo 메서드'
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: dc255323f103b3422b927b0489402b24767dcd92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737846"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="f02f2-103">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f02f2-103">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="f02f2-104">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f02f2-104">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02f2-105">구문</span><span class="sxs-lookup"><span data-stu-id="f02f2-105">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f02f2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f02f2-106">Parameters</span></span>  
  
|<span data-ttu-id="f02f2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f02f2-107">Parameter</span></span>|<span data-ttu-id="f02f2-108">설명</span><span class="sxs-lookup"><span data-stu-id="f02f2-108">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f02f2-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="f02f2-109">Return Value</span></span>  

 <span data-ttu-id="f02f2-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f02f2-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f02f2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f02f2-111">Requirements</span></span>  

 <span data-ttu-id="f02f2-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f02f2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02f2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f02f2-113">See also</span></span>

- [<span data-ttu-id="f02f2-114">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f02f2-114">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
