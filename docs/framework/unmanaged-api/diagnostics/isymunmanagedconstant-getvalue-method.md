---
description: '자세히 알아보기: ISymUnmanagedConstant:: GetValue 메서드'
title: ISymUnmanagedConstant::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 05818028deb804bf2a2426285b5185b01776199d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689692"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="bcefe-103">ISymUnmanagedConstant::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="bcefe-103">ISymUnmanagedConstant::GetValue Method</span></span>

<span data-ttu-id="bcefe-104"> 상수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bcefe-104">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcefe-105">구문</span><span class="sxs-lookup"><span data-stu-id="bcefe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcefe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bcefe-106">Parameters</span></span>  

 `pValue`  
 <span data-ttu-id="bcefe-107">제한이 값을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bcefe-107">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcefe-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="bcefe-108">Return Value</span></span>  

 <span data-ttu-id="bcefe-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bcefe-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcefe-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bcefe-110">Requirements</span></span>  

 <span data-ttu-id="bcefe-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bcefe-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcefe-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcefe-112">See also</span></span>

- [<span data-ttu-id="bcefe-113">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bcefe-113">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="bcefe-114">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="bcefe-114">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="bcefe-115">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="bcefe-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
