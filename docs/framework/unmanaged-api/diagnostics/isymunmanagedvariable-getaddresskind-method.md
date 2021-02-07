---
description: '자세한 정보: ISymUnmanagedVariable:: Getaddres Ind 메서드'
title: ISymUnmanagedVariable::GetAddressKind 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 4b090560335432ad39157fee987ce15728fece63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762853"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="d8e30-103">ISymUnmanagedVariable::GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="d8e30-103">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="d8e30-104">이 변수의 주소 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8e30-104">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e30-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8e30-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8e30-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8e30-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="d8e30-107">제한이 값을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e30-107">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="d8e30-108">가능한 값은 [CorSymAddrKind](corsymaddrkind-enumeration.md) 열거형에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e30-108">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8e30-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d8e30-109">Return Value</span></span>  

 <span data-ttu-id="d8e30-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e30-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e30-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8e30-111">Requirements</span></span>  

 <span data-ttu-id="d8e30-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d8e30-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e30-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8e30-113">See also</span></span>

- [<span data-ttu-id="d8e30-114">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8e30-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
