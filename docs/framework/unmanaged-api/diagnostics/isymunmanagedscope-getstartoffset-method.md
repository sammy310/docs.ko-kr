---
title: ISymUnmanagedScope::GetStartOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faab55199a3b921ea8b995e2a0f9823fb4da9cc7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230592"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="94900-102">ISymUnmanagedScope::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="94900-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="94900-103">이 범위에 대 한 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94900-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94900-104">구문</span><span class="sxs-lookup"><span data-stu-id="94900-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94900-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94900-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="94900-106">[out] 에 대 한 포인터를 `ULONG32` 시작 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="94900-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94900-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="94900-107">Return Value</span></span>  
 <span data-ttu-id="94900-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="94900-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94900-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94900-109">Requirements</span></span>  
 <span data-ttu-id="94900-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="94900-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94900-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="94900-111">See also</span></span>

- [<span data-ttu-id="94900-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94900-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="94900-113">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="94900-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
