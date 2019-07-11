---
title: ISymUnmanagedVariable::GetAddressField1 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a035e8dd7bd880c4ead500eede5e1b095d701f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778063"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="37d62-102">ISymUnmanagedVariable::GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="37d62-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="37d62-103">이 변수에 대 한 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37d62-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="37d62-104">해당 의미는 주소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="37d62-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37d62-105">구문</span><span class="sxs-lookup"><span data-stu-id="37d62-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37d62-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37d62-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="37d62-107">[out] 에 대 한 포인터를 `ULONG32` 첫 번째 주소 필드를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="37d62-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37d62-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="37d62-108">Return Value</span></span>  
 <span data-ttu-id="37d62-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="37d62-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37d62-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37d62-110">Requirements</span></span>  
 <span data-ttu-id="37d62-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="37d62-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d62-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="37d62-112">See also</span></span>

- [<span data-ttu-id="37d62-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37d62-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="37d62-114">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="37d62-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="37d62-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="37d62-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="37d62-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="37d62-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
