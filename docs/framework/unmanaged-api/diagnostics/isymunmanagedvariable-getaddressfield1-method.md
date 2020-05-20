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
ms.openlocfilehash: 253fd17178c03bc0c4d8ea031888a404ad56f876
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615282"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="c6e74-102">ISymUnmanagedVariable::GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="c6e74-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="c6e74-103">이 변수의 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6e74-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="c6e74-104">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c6e74-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e74-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6e74-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6e74-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6e74-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c6e74-107">제한이 `ULONG32`첫 번째 주소 필드를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e74-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6e74-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c6e74-108">Return Value</span></span>  
 <span data-ttu-id="c6e74-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c6e74-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6e74-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6e74-110">Requirements</span></span>  
 <span data-ttu-id="c6e74-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c6e74-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e74-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6e74-112">See also</span></span>

- [<span data-ttu-id="c6e74-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6e74-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="c6e74-114">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="c6e74-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="c6e74-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="c6e74-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="c6e74-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="c6e74-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
