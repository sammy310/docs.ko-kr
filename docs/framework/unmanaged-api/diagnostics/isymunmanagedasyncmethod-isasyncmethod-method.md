---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129204"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="c8136-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="c8136-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="c8136-103">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8136-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="c8136-104">이 메서드가 `FALSE` 반환 하는 경우이 인터페이스의 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8136-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="c8136-105">이 경우 모두 `E_UNEXPECTED` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8136-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8136-106">구문</span><span class="sxs-lookup"><span data-stu-id="c8136-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8136-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8136-107">Parameters</span></span>  
  
|<span data-ttu-id="c8136-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8136-108">Parameter</span></span>|<span data-ttu-id="c8136-109">설명</span><span class="sxs-lookup"><span data-stu-id="c8136-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="c8136-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c8136-110">Return Value</span></span>  
 <span data-ttu-id="c8136-111">`HRESULT`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c8136-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8136-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8136-112">Requirements</span></span>  
 <span data-ttu-id="c8136-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c8136-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8136-114">참조</span><span class="sxs-lookup"><span data-stu-id="c8136-114">See also</span></span>

- [<span data-ttu-id="c8136-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8136-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
