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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e686e332cf1d35537e5d4306a3a9cbf9d46c47e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752372"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="81f9f-102">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="81f9f-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="81f9f-103">메서드를 열고 하 고 이미지의 해당 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f9f-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="81f9f-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81f9f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81f9f-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="81f9f-106">[in] 열려는 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="81f9f-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="81f9f-107">[in] 이미지 섹션 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="81f9f-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="81f9f-108">[in] 이미지 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="81f9f-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81f9f-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="81f9f-109">Return Value</span></span>  
 <span data-ttu-id="81f9f-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="81f9f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81f9f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81f9f-111">Requirements</span></span>  
 <span data-ttu-id="81f9f-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="81f9f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f9f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="81f9f-113">See also</span></span>

- [<span data-ttu-id="81f9f-114">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81f9f-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="81f9f-115">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="81f9f-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
