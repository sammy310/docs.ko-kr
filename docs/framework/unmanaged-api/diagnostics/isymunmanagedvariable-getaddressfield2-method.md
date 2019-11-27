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
ms.openlocfilehash: 794615994cd11ee00c2a381b9ba883cebb8233a0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446116"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="569d8-102">ISymUnmanagedVariable::GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="569d8-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="569d8-103">이 변수의 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="569d8-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="569d8-104">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="569d8-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="569d8-105">구문</span><span class="sxs-lookup"><span data-stu-id="569d8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="569d8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="569d8-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="569d8-107">제한이 두 번째 주소 필드를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="569d8-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="569d8-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="569d8-108">Return Value</span></span>  
 <span data-ttu-id="569d8-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="569d8-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="569d8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="569d8-110">Requirements</span></span>  
 <span data-ttu-id="569d8-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="569d8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="569d8-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="569d8-112">See also</span></span>

- [<span data-ttu-id="569d8-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="569d8-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="569d8-114">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="569d8-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="569d8-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="569d8-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="569d8-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="569d8-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
