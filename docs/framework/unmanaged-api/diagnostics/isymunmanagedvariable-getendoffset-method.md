---
title: ISymUnmanagedVariable::GetEndOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 325db05cc322d85e836ca9ba62b6a169e8965241
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220957"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="72535-102">ISymUnmanagedVariable::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="72535-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="72535-103">부모 내에서이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72535-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="72535-104">범위 내에서 로컬 변수 이면 끝 오프셋 범위에 대해 정의 된 오프셋 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72535-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72535-105">구문</span><span class="sxs-lookup"><span data-stu-id="72535-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72535-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72535-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="72535-107">[out] 에 대 한 포인터를 `ULONG32` 를 받는 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="72535-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72535-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="72535-108">Return Value</span></span>  
 <span data-ttu-id="72535-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="72535-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72535-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72535-110">Requirements</span></span>  
 <span data-ttu-id="72535-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72535-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72535-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="72535-112">See also</span></span>

- [<span data-ttu-id="72535-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72535-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="72535-114">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="72535-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
