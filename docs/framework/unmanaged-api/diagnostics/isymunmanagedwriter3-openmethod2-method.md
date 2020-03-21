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
ms.openlocfilehash: 0c112819ef3bc4f9a7146ee80f55202ff89d689a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178324"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="a53e3-102">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="a53e3-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="a53e3-103">메서드를 열고 이미지에서 실제 섹션 오프셋을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a53e3-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a53e3-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a53e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a53e3-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="a53e3-106">【인】 메서드를 여는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a53e3-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="a53e3-107">【인】 이미지의 섹션 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a53e3-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="a53e3-108">【인】 이미지의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="a53e3-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a53e3-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="a53e3-109">Return Value</span></span>  
 <span data-ttu-id="a53e3-110">메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL 또는 다른 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a53e3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53e3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a53e3-111">Requirements</span></span>  
 <span data-ttu-id="a53e3-112">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="a53e3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53e3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a53e3-113">See also</span></span>

- [<span data-ttu-id="a53e3-114">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a53e3-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="a53e3-115">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a53e3-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
