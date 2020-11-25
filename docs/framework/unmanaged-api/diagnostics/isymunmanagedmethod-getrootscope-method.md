---
title: ISymUnmanagedMethod::GetRootScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: 071738c8fb9b40457215e21172240aa7e77198cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699471"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="16696-102">ISymUnmanagedMethod::GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="16696-102">ISymUnmanagedMethod::GetRootScope Method</span></span>

<span data-ttu-id="16696-103">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16696-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="16696-104">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="16696-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16696-105">구문</span><span class="sxs-lookup"><span data-stu-id="16696-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16696-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16696-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="16696-107">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16696-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16696-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="16696-108">Return Value</span></span>  

 <span data-ttu-id="16696-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="16696-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16696-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16696-110">Requirements</span></span>  

 <span data-ttu-id="16696-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="16696-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16696-112">참조</span><span class="sxs-lookup"><span data-stu-id="16696-112">See also</span></span>

- [<span data-ttu-id="16696-113">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16696-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
