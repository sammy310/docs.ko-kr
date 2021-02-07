---
description: '자세히 알아보기: ISymUnmanagedScope:: GetChildren 메서드'
title: ISymUnmanagedScope::GetChildren 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: 55d72c98d34fcb30a479611895228fbc1b9f7f55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763503"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="3abd6-103">ISymUnmanagedScope::GetChildren 메서드</span><span class="sxs-lookup"><span data-stu-id="3abd6-103">ISymUnmanagedScope::GetChildren Method</span></span>

<span data-ttu-id="3abd6-104">이 범위의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3abd6-104">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abd6-105">구문</span><span class="sxs-lookup"><span data-stu-id="3abd6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3abd6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3abd6-106">Parameters</span></span>  

 `cChildren`  
 <span data-ttu-id="3abd6-107">진행 `ULONG32` 배열의 크기를 나타내는입니다 `children` .</span><span class="sxs-lookup"><span data-stu-id="3abd6-107">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="3abd6-108">제한이 `ULONG32` 자식을 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3abd6-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="3abd6-109">제한이 반환 된 자식의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3abd6-109">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3abd6-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="3abd6-110">Return Value</span></span>  

 <span data-ttu-id="3abd6-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3abd6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abd6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3abd6-112">Requirements</span></span>  

 <span data-ttu-id="3abd6-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3abd6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abd6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3abd6-114">See also</span></span>

- [<span data-ttu-id="3abd6-115">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3abd6-115">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="3abd6-116">GetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="3abd6-116">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
