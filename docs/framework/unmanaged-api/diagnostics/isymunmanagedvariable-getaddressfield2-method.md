---
title: ISymUnmanagedVariable::GetAddressField2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2030a0da7a84695750d1dd9781adca9cd66f22ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797620"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="79032-102">ISymUnmanagedVariable::GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="79032-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="79032-103">이 변수에 대 한 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79032-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="79032-104">해당 의미는 주소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="79032-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79032-105">구문</span><span class="sxs-lookup"><span data-stu-id="79032-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79032-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79032-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="79032-107">[out] 에 대 한 포인터를 `ULONG32` 를 받는 두 번째 주소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="79032-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79032-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="79032-108">Return Value</span></span>  
 <span data-ttu-id="79032-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="79032-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79032-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79032-110">Requirements</span></span>  
 <span data-ttu-id="79032-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="79032-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79032-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="79032-112">See also</span></span>

- [<span data-ttu-id="79032-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79032-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="79032-114">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="79032-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="79032-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="79032-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="79032-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="79032-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
