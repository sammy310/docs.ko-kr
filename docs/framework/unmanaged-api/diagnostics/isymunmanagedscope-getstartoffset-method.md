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
ms.openlocfilehash: 071ad6c24804eecb0f2260d54c854f22ff997bc1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611018"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="598ae-102">ISymUnmanagedScope::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="598ae-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="598ae-103">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="598ae-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="598ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="598ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="598ae-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="598ae-106">제한이 시작 오프셋을 포함 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="598ae-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598ae-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="598ae-107">Return Value</span></span>  
 <span data-ttu-id="598ae-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="598ae-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598ae-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="598ae-109">Requirements</span></span>  
 <span data-ttu-id="598ae-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="598ae-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598ae-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="598ae-111">See also</span></span>

- [<span data-ttu-id="598ae-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="598ae-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="598ae-113">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="598ae-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
