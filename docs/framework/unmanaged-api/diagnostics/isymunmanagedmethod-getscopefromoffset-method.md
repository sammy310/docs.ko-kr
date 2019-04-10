---
title: ISymUnmanagedMethod::GetScopeFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0e859ba8b6ec247073b0b69b035ea4cf074ab05
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149294"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="e115d-102">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="e115d-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="e115d-103">지정 된 오프셋을 포함 하는이 메서드 내에서 가장 바깥쪽 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e115d-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="e115d-104">이 지역 변수 검색을 시작 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e115d-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e115d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e115d-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e115d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e115d-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="e115d-107">[in] `ULONG` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e115d-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e115d-108">[out] 설정 된 포인터를 반환 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e115d-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e115d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e115d-109">Return Value</span></span>  
 <span data-ttu-id="e115d-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e115d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e115d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e115d-111">Requirements</span></span>  
 <span data-ttu-id="e115d-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e115d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e115d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e115d-113">See also</span></span>

- [<span data-ttu-id="e115d-114">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e115d-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
