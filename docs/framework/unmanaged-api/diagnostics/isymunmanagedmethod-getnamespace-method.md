---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetNamespace 메서드'
title: ISymUnmanagedMethod::GetNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: 8cb211b1047aff31cc4f12d538fee414c578155b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721413"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="075d4-103">ISymUnmanagedMethod::GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="075d4-103">ISymUnmanagedMethod::GetNamespace Method</span></span>

<span data-ttu-id="075d4-104">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="075d4-104">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="075d4-105">구문</span><span class="sxs-lookup"><span data-stu-id="075d4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="075d4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="075d4-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="075d4-107">제한이 반환 된 [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="075d4-107">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="075d4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="075d4-108">Return Value</span></span>  

 <span data-ttu-id="075d4-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="075d4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="075d4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="075d4-110">Requirements</span></span>  

 <span data-ttu-id="075d4-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="075d4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075d4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="075d4-112">See also</span></span>

- [<span data-ttu-id="075d4-113">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="075d4-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
