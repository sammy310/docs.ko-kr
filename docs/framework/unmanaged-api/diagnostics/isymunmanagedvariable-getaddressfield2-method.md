---
description: '자세히 알아보기: ISymUnmanagedVariable:: GetAddressField2 메서드'
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
ms.openlocfilehash: 5d9bc226bfc462157e66b1d8fb43762945cdc016
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762970"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="5df09-103">ISymUnmanagedVariable::GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="5df09-103">ISymUnmanagedVariable::GetAddressField2 Method</span></span>

<span data-ttu-id="5df09-104">이 변수의 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5df09-104">Gets the second address field for this variable.</span></span> <span data-ttu-id="5df09-105">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5df09-105">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df09-106">구문</span><span class="sxs-lookup"><span data-stu-id="5df09-106">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5df09-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5df09-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="5df09-108">제한이 `ULONG32` 두 번째 주소 필드를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5df09-108">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5df09-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5df09-109">Return Value</span></span>  

 <span data-ttu-id="5df09-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5df09-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5df09-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5df09-111">Requirements</span></span>  

 <span data-ttu-id="5df09-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5df09-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df09-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5df09-113">See also</span></span>

- [<span data-ttu-id="5df09-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5df09-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="5df09-115">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="5df09-115">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="5df09-116">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="5df09-116">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="5df09-117">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="5df09-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
