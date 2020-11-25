---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 메서드
ms.date: 03/30/2017
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
ms.openlocfilehash: 997e8b95e5e088e4b403822bb94577b3a9c2e6e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732907"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="1a335-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount 메서드</span><span class="sxs-lookup"><span data-stu-id="1a335-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>

<span data-ttu-id="1a335-103">[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a335-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a335-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a335-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a335-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a335-105">Parameters</span></span>  
  
|<span data-ttu-id="1a335-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a335-106">Parameter</span></span>|<span data-ttu-id="1a335-107">설명</span><span class="sxs-lookup"><span data-stu-id="1a335-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="1a335-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a335-108">Return Value</span></span>  

 <span data-ttu-id="1a335-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1a335-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a335-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a335-110">Requirements</span></span>  

 <span data-ttu-id="1a335-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="1a335-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a335-112">참조</span><span class="sxs-lookup"><span data-stu-id="1a335-112">See also</span></span>

- [<span data-ttu-id="1a335-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a335-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
