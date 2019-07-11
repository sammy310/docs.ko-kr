---
title: ISymUnmanagedVariable::GetSignature 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abd4bb00f5c1e703740462f1709407616ac8a8e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778233"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="e6344-102">ISymUnmanagedVariable::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="e6344-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="e6344-103">이 변수 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6344-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6344-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6344-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6344-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e6344-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="e6344-106">[in] 가리키는 버퍼의 길이 `sig` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e6344-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="e6344-107">[out] 에 대 한 포인터를 `ULONG32` 문자 시그니처를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6344-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="e6344-108">[out] 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e6344-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6344-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e6344-109">Return Value</span></span>  
 <span data-ttu-id="e6344-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e6344-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6344-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6344-111">Requirements</span></span>  
 <span data-ttu-id="e6344-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e6344-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6344-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6344-113">See also</span></span>

- [<span data-ttu-id="e6344-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6344-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
