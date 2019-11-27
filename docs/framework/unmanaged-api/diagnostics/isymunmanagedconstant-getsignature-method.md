---
title: ISymUnmanagedConstant::GetSignature 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 401dfbea0da309db24f3052f462daa66e8bbef4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449274"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="04beb-102">ISymUnmanagedConstant::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="04beb-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="04beb-103">상수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04beb-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04beb-104">구문</span><span class="sxs-lookup"><span data-stu-id="04beb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04beb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04beb-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="04beb-106">진행 `pcSig` 매개 변수가 가리키는 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="04beb-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="04beb-107">제한이 서명을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04beb-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="04beb-108">제한이 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="04beb-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04beb-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="04beb-109">Return Value</span></span>  
 <span data-ttu-id="04beb-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="04beb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04beb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04beb-111">Requirements</span></span>  
 <span data-ttu-id="04beb-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="04beb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04beb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04beb-113">See also</span></span>

- [<span data-ttu-id="04beb-114">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04beb-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="04beb-115">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="04beb-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="04beb-116">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="04beb-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
