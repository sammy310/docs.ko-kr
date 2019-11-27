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
ms.openlocfilehash: a59b50009e7f0ab2fff1b8439e368234403822c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446138"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="c3e63-102">ISymUnmanagedVariable::GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="c3e63-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="c3e63-103">이 변수의 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3e63-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="c3e63-104">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c3e63-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e63-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3e63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3e63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3e63-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c3e63-107">제한이 첫 번째 주소 필드를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e63-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3e63-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3e63-108">Return Value</span></span>  
 <span data-ttu-id="c3e63-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e63-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3e63-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3e63-110">Requirements</span></span>  
 <span data-ttu-id="c3e63-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c3e63-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e63-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3e63-112">See also</span></span>

- [<span data-ttu-id="c3e63-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3e63-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c3e63-114">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="c3e63-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="c3e63-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="c3e63-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="c3e63-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="c3e63-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
