---
title: ISymUnmanagedWriter2::DefineConstant2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e9bff5be747c4872554a69dd316de8ca9eb9934
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198935"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="fb2cd-102">ISymUnmanagedWriter2::DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="fb2cd-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="fb2cd-103">상수 값에 대 한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cd-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb2cd-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb2cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb2cd-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fb2cd-106">[in] 상수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cd-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="fb2cd-107">[in] 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cd-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="fb2cd-108">[in] 메타 데이터 토큰 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cd-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb2cd-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="fb2cd-109">Return Value</span></span>  
 <span data-ttu-id="fb2cd-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2cd-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb2cd-111">Requirements</span></span>  
 <span data-ttu-id="fb2cd-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb2cd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2cd-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb2cd-113">See also</span></span>

- [<span data-ttu-id="fb2cd-114">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb2cd-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="fb2cd-115">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="fb2cd-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
