---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707154"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="8e90d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="8e90d-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="8e90d-103">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e90d-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="8e90d-104">이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e90d-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="8e90d-105">이 경우 모두 반환 됩니다 `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="8e90d-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e90d-106">구문</span><span class="sxs-lookup"><span data-stu-id="8e90d-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e90d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e90d-107">Parameters</span></span>  
  
|<span data-ttu-id="8e90d-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e90d-108">Parameter</span></span>|<span data-ttu-id="8e90d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8e90d-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="8e90d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="8e90d-110">Return Value</span></span>  

 <span data-ttu-id="8e90d-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8e90d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e90d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e90d-112">Requirements</span></span>  

 <span data-ttu-id="8e90d-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8e90d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e90d-114">참조</span><span class="sxs-lookup"><span data-stu-id="8e90d-114">See also</span></span>

- [<span data-ttu-id="8e90d-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e90d-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
