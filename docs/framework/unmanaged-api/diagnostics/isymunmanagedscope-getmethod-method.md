---
description: '자세히 알아보기: ISymUnmanagedScope:: GetMethod 메서드'
title: ISymUnmanagedScope::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: 7dfc5f41d849d47bfaf600e40a7ccc9dd45da676
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763399"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="5ae2a-103">ISymUnmanagedScope::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="5ae2a-103">ISymUnmanagedScope::GetMethod Method</span></span>

<span data-ttu-id="5ae2a-104">이 범위를 포함 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-104">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="5ae2a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ae2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ae2a-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="5ae2a-107">제한이 반환 된 [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-107">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ae2a-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="5ae2a-108">Return Value</span></span>  

 <span data-ttu-id="5ae2a-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae2a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae2a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ae2a-110">Requirements</span></span>  

 <span data-ttu-id="5ae2a-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5ae2a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae2a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ae2a-112">See also</span></span>

- [<span data-ttu-id="5ae2a-113">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ae2a-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
