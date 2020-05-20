---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441801"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="ff0ab-102">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="ff0ab-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="ff0ab-103">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="ff0ab-104">이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="ff0ab-105">이 경우 모두 반환 됩니다 `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="ff0ab-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff0ab-106">구문</span><span class="sxs-lookup"><span data-stu-id="ff0ab-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff0ab-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff0ab-107">Parameters</span></span>  
  
|<span data-ttu-id="ff0ab-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff0ab-108">Parameter</span></span>|<span data-ttu-id="ff0ab-109">설명</span><span class="sxs-lookup"><span data-stu-id="ff0ab-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="ff0ab-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="ff0ab-110">Return Value</span></span>  
 <span data-ttu-id="ff0ab-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff0ab-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff0ab-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff0ab-112">Requirements</span></span>  
 <span data-ttu-id="ff0ab-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ff0ab-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0ab-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff0ab-114">See also</span></span>

- [<span data-ttu-id="ff0ab-115">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff0ab-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
