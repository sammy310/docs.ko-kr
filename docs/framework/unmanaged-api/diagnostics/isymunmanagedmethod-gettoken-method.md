---
title: ISymUnmanagedMethod::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ec6e25452a40ae67570badde8a883878d103f95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939570"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="3945a-102">ISymUnmanagedMethod::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="3945a-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="3945a-103">이 메서드에 대 한 메타 데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3945a-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3945a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3945a-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3945a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3945a-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="3945a-106">[out] 에 대 한 포인터를 `mdMethodDef` 문자 메타 데이터를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3945a-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3945a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3945a-107">Return Value</span></span>  
 <span data-ttu-id="3945a-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3945a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3945a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3945a-109">Requirements</span></span>  
 <span data-ttu-id="3945a-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3945a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3945a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="3945a-111">See also</span></span>

- [<span data-ttu-id="3945a-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3945a-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
