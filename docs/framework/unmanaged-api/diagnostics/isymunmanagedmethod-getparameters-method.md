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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a757e3b28a94c96e28a5bab736a6820a83617a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939635"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="efa31-102">ISymUnmanagedMethod::GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="efa31-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="efa31-103">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-103">Gets the parameters for this method.</span></span> <span data-ttu-id="efa31-104">매개 변수는 메서드 시그니처 내의 정의 된 순서 대로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa31-105">구문</span><span class="sxs-lookup"><span data-stu-id="efa31-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa31-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efa31-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="efa31-107">[in] `params` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="efa31-108">[in] 에 대 한 포인터를 `ULONG32` 매개 변수를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="efa31-109">[out] 매개 변수를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efa31-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="efa31-110">Return Value</span></span>  
 <span data-ttu-id="efa31-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="efa31-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa31-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efa31-112">Requirements</span></span>  
 <span data-ttu-id="efa31-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="efa31-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa31-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="efa31-114">See also</span></span>

- [<span data-ttu-id="efa31-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efa31-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
