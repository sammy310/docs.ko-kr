---
title: ISymUnmanagedWriter3::OpenMethod2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438132"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="9395e-102">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="9395e-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="9395e-103">Opens a method and provides its real section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="9395e-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9395e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9395e-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9395e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9395e-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="9395e-106">[in] The metadata token for the method to be opened.</span><span class="sxs-lookup"><span data-stu-id="9395e-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="9395e-107">[in] The section offset in the image.</span><span class="sxs-lookup"><span data-stu-id="9395e-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="9395e-108">[in] The offset in the image.</span><span class="sxs-lookup"><span data-stu-id="9395e-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9395e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="9395e-109">Return Value</span></span>  
 <span data-ttu-id="9395e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="9395e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9395e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9395e-111">Requirements</span></span>  
 <span data-ttu-id="9395e-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9395e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9395e-113">참조</span><span class="sxs-lookup"><span data-stu-id="9395e-113">See also</span></span>

- [<span data-ttu-id="9395e-114">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9395e-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="9395e-115">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="9395e-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
