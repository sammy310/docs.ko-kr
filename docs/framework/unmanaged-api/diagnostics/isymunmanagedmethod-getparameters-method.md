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
ms.openlocfilehash: c66fd810ae4976bc0b5e04572b899465cebe4bbb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699510"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="c7a63-102">ISymUnmanagedMethod::GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="c7a63-102">ISymUnmanagedMethod::GetParameters Method</span></span>

<span data-ttu-id="c7a63-103">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-103">Gets the parameters for this method.</span></span> <span data-ttu-id="c7a63-104">매개 변수는 메서드 서명 내에서 정의 된 순서 대로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a63-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7a63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7a63-106">Parameters</span></span>  

 `cParams`  
 <span data-ttu-id="c7a63-107">[in] `params` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="c7a63-108">진행 `ULONG32` 매개 변수를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="c7a63-109">제한이 매개 변수를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7a63-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7a63-110">Return Value</span></span>  

 <span data-ttu-id="c7a63-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c7a63-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a63-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7a63-112">Requirements</span></span>  

 <span data-ttu-id="c7a63-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c7a63-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a63-114">참조</span><span class="sxs-lookup"><span data-stu-id="c7a63-114">See also</span></span>

- [<span data-ttu-id="c7a63-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7a63-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
