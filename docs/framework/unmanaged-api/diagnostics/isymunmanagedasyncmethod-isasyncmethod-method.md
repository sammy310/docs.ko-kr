---
description: '자세히 알아보기: ISymUnmanagedAsyncMethod:: IsAsyncMethod 메서드'
title: ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 4b151f5367bac5fd92cc8237492cad6dacfb8e88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790258"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="b45c9-103">ISymUnmanagedAsyncMethod::IsAsyncMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="b45c9-103">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="b45c9-104">메서드에 비동기 정보가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45c9-104">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="b45c9-105">이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b45c9-105">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="b45c9-106">이 경우 모두 반환 됩니다 `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="b45c9-106">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b45c9-107">구문</span><span class="sxs-lookup"><span data-stu-id="b45c9-107">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b45c9-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b45c9-108">Parameters</span></span>  
  
|<span data-ttu-id="b45c9-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b45c9-109">Parameter</span></span>|<span data-ttu-id="b45c9-110">설명</span><span class="sxs-lookup"><span data-stu-id="b45c9-110">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="b45c9-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="b45c9-111">Return Value</span></span>  

 <span data-ttu-id="b45c9-112">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b45c9-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b45c9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b45c9-113">Requirements</span></span>  

 <span data-ttu-id="b45c9-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="b45c9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45c9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b45c9-115">See also</span></span>

- [<span data-ttu-id="b45c9-116">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b45c9-116">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
