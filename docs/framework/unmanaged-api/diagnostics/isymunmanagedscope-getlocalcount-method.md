---
description: '자세히 알아보기: ISymUnmanagedScope:: GetLocalCount 메서드'
title: ISymUnmanagedScope::GetLocalCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 987d161d273b12810988ef30acb703973098d29c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763442"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="54b33-103">ISymUnmanagedScope::GetLocalCount 메서드</span><span class="sxs-lookup"><span data-stu-id="54b33-103">ISymUnmanagedScope::GetLocalCount Method</span></span>

<span data-ttu-id="54b33-104">이 범위 내에 정의 된 지역 변수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54b33-104">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b33-105">구문</span><span class="sxs-lookup"><span data-stu-id="54b33-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54b33-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54b33-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="54b33-107">제한이 `ULONG32` 지역 변수의 개수를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54b33-107">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54b33-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="54b33-108">Return Value</span></span>  

 <span data-ttu-id="54b33-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="54b33-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b33-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54b33-110">Requirements</span></span>  

 <span data-ttu-id="54b33-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="54b33-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b33-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54b33-112">See also</span></span>

- [<span data-ttu-id="54b33-113">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54b33-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
