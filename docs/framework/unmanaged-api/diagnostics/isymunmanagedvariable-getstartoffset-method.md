---
title: ISymUnmanagedVariable::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a30dff869075a201a669d1e703bc003b011fc3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196283"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="6cf0b-102">ISymUnmanagedVariable::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6cf0b-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="6cf0b-103">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cf0b-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="6cf0b-104">범위 내에서 로컬 변수 이면 시작 오프셋 범위에 대해 정의 된 오프셋 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cf0b-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cf0b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cf0b-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cf0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6cf0b-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6cf0b-107">[out] 에 대 한 포인터를 `ULONG32` 시작 오프셋을 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="6cf0b-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cf0b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6cf0b-108">Return Value</span></span>  
 <span data-ttu-id="6cf0b-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6cf0b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cf0b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cf0b-110">Requirements</span></span>  
 <span data-ttu-id="6cf0b-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6cf0b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf0b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="6cf0b-112">See also</span></span>

- [<span data-ttu-id="6cf0b-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6cf0b-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="6cf0b-114">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6cf0b-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
