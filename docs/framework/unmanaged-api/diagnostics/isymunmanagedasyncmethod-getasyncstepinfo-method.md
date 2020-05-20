---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: e3c0d7b8eeded403ce8391cff00ee18dccc38ed5
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441892"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="eeafa-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="eeafa-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="eeafa-103">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eeafa-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeafa-104">구문</span><span class="sxs-lookup"><span data-stu-id="eeafa-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeafa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eeafa-105">Parameters</span></span>  
  
|<span data-ttu-id="eeafa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eeafa-106">Parameter</span></span>|<span data-ttu-id="eeafa-107">설명</span><span class="sxs-lookup"><span data-stu-id="eeafa-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="eeafa-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="eeafa-108">Return Value</span></span>  
 <span data-ttu-id="eeafa-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eeafa-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeafa-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eeafa-110">Requirements</span></span>  
 <span data-ttu-id="eeafa-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="eeafa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeafa-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeafa-112">See also</span></span>

- [<span data-ttu-id="eeafa-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeafa-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
