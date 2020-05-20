---
title: ISymUnmanagedMethod::GetParameters 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: 031e9d9434bc655ba8947a2bb6aba56a150e9002
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614463"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="bd366-102">ISymUnmanagedMethod::GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="bd366-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="bd366-103">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-103">Gets the parameters for this method.</span></span> <span data-ttu-id="bd366-104">매개 변수는 메서드 서명 내에서 정의 된 순서 대로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd366-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd366-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd366-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd366-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="bd366-107">[in] `params` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="bd366-108">진행 `ULONG32`매개 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="bd366-109">제한이 매개 변수를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd366-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="bd366-110">Return Value</span></span>  
 <span data-ttu-id="bd366-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bd366-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd366-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd366-112">Requirements</span></span>  
 <span data-ttu-id="bd366-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bd366-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd366-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd366-114">See also</span></span>

- [<span data-ttu-id="bd366-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd366-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
