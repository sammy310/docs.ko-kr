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
ms.openlocfilehash: 76134a2447cbc40b5c97304540d9907648bc89e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719920"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="cdabd-102">ISymUnmanagedMethod::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="cdabd-102">ISymUnmanagedMethod::GetToken Method</span></span>

<span data-ttu-id="cdabd-103">이 메서드에 대한 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cdabd-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdabd-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdabd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdabd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdabd-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="cdabd-106">제한이 `mdMethodDef` 메타 데이터를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdabd-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdabd-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cdabd-107">Return Value</span></span>  

 <span data-ttu-id="cdabd-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cdabd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdabd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdabd-109">Requirements</span></span>  

 <span data-ttu-id="cdabd-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cdabd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdabd-111">참조</span><span class="sxs-lookup"><span data-stu-id="cdabd-111">See also</span></span>

- [<span data-ttu-id="cdabd-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdabd-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
