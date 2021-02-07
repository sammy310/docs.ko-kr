---
description: '자세히 알아보기: ISymUnmanagedScope:: GetStartOffset 메서드'
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
ms.openlocfilehash: c95fbc5229512f08052ffc00f0092f64983ea3f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763321"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="159d3-103">ISymUnmanagedScope::GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="159d3-103">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="159d3-104">이 범위의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="159d3-104">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159d3-105">구문</span><span class="sxs-lookup"><span data-stu-id="159d3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="159d3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="159d3-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="159d3-107">제한이 시작 오프셋을 포함 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="159d3-107">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="159d3-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="159d3-108">Return Value</span></span>  

 <span data-ttu-id="159d3-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="159d3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="159d3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="159d3-110">Requirements</span></span>  

 <span data-ttu-id="159d3-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="159d3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159d3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="159d3-112">See also</span></span>

- [<span data-ttu-id="159d3-113">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="159d3-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="159d3-114">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="159d3-114">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
