---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174943"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="61675-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="61675-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="61675-103">참조 [DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61675-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61675-104">구문</span><span class="sxs-lookup"><span data-stu-id="61675-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61675-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61675-105">Parameters</span></span>  
  
|<span data-ttu-id="61675-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61675-106">Parameter</span></span>|<span data-ttu-id="61675-107">설명</span><span class="sxs-lookup"><span data-stu-id="61675-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="61675-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="61675-108">Return Value</span></span>  
 <span data-ttu-id="61675-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61675-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61675-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61675-110">Requirements</span></span>  
 <span data-ttu-id="61675-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61675-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61675-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="61675-112">See also</span></span>

- [<span data-ttu-id="61675-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61675-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
