---
description: '자세히 알아보기: ISymUnmanagedScope2:: GetConstantCount 메서드'
title: ISymUnmanagedScope2::GetConstantCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: e5b084edb116432aa43360db72ca2528dd3cc6a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763256"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="85e9d-103">ISymUnmanagedScope2::GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="85e9d-103">ISymUnmanagedScope2::GetConstantCount Method</span></span>

<span data-ttu-id="85e9d-104">이 범위 내에 정의 된 상수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85e9d-104">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e9d-105">구문</span><span class="sxs-lookup"><span data-stu-id="85e9d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85e9d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85e9d-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="85e9d-107">제한이 `ULONG32` 상수를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="85e9d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85e9d-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="85e9d-108">Return Value</span></span>  

 <span data-ttu-id="85e9d-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="85e9d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e9d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85e9d-110">Requirements</span></span>  

 <span data-ttu-id="85e9d-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="85e9d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e9d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85e9d-112">See also</span></span>

- [<span data-ttu-id="85e9d-113">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85e9d-113">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
