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
ms.openlocfilehash: 650a64e72b410cddfbee7dce676ddbb5a3b8b3d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614450"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="1edd7-102">ISymUnmanagedMethod::GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="1edd7-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="1edd7-103">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1edd7-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="1edd7-104">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1edd7-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1edd7-105">구문</span><span class="sxs-lookup"><span data-stu-id="1edd7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1edd7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1edd7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1edd7-107">제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1edd7-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1edd7-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="1edd7-108">Return Value</span></span>  
 <span data-ttu-id="1edd7-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1edd7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1edd7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1edd7-110">Requirements</span></span>  
 <span data-ttu-id="1edd7-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="1edd7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edd7-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1edd7-112">See also</span></span>

- [<span data-ttu-id="1edd7-113">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1edd7-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
