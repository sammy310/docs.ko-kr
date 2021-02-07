---
description: '자세히 알아보기: ISymUnmanagedScope:: GetEndOffset 메서드'
title: ISymUnmanagedScope::GetEndOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: ac95b98bb87fbf3dc3b42b5a2e5413f76dfffa34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763478"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="235b7-103">ISymUnmanagedScope::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="235b7-103">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="235b7-104">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="235b7-104">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="235b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="235b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="235b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="235b7-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="235b7-107">제한이 `ULONG32` 끝 오프셋을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="235b7-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="235b7-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="235b7-108">Return Value</span></span>  

 <span data-ttu-id="235b7-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="235b7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="235b7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="235b7-110">Requirements</span></span>  

 <span data-ttu-id="235b7-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="235b7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235b7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="235b7-112">See also</span></span>

- [<span data-ttu-id="235b7-113">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="235b7-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="235b7-114">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="235b7-114">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
