---
title: ISymUnmanagedScope2::GetConstants 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08bc85c7a5b53c145375ca34f11ec499e5e7528f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761587"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="c8410-102">ISymUnmanagedScope2::GetConstants 메서드</span><span class="sxs-lookup"><span data-stu-id="c8410-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="c8410-103">이 범위 내에 정의 된 지역 상수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8410-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8410-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8410-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8410-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8410-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="c8410-106">[in] 버퍼의 길이는 `pcConstants` 매개 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c8410-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="c8410-107">[out] 에 대 한 포인터를 `ULONG32` 문자 상수를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8410-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="c8410-108">[out] 상수를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c8410-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8410-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c8410-109">Return Value</span></span>  
 <span data-ttu-id="c8410-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c8410-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8410-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8410-111">Requirements</span></span>  
 <span data-ttu-id="c8410-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8410-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8410-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8410-113">See also</span></span>

- [<span data-ttu-id="c8410-114">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8410-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
