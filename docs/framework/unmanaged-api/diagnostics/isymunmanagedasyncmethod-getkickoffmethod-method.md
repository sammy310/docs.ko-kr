---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 58daec30b4cbae9cfaab27d4ce76521ba839cf83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139837"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="4f9ab-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="4f9ab-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="4f9ab-103">[DefineKickoffMethod 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f9ab-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f9ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f9ab-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f9ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f9ab-105">Parameters</span></span>  
  
|<span data-ttu-id="4f9ab-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f9ab-106">Parameter</span></span>|<span data-ttu-id="4f9ab-107">설명</span><span class="sxs-lookup"><span data-stu-id="4f9ab-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="4f9ab-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4f9ab-108">Return Value</span></span>  
 <span data-ttu-id="4f9ab-109">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ab-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f9ab-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f9ab-110">Requirements</span></span>  
 <span data-ttu-id="4f9ab-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4f9ab-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9ab-112">참조</span><span class="sxs-lookup"><span data-stu-id="4f9ab-112">See also</span></span>

- [<span data-ttu-id="4f9ab-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f9ab-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
