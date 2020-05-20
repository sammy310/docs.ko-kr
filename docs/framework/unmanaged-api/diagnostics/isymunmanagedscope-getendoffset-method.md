---
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
ms.openlocfilehash: 4d6bd239a15bd196f840007af120cb062499f4c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614853"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="afa29-102">ISymUnmanagedScope::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="afa29-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="afa29-103">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="afa29-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa29-104">구문</span><span class="sxs-lookup"><span data-stu-id="afa29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afa29-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="afa29-106">제한이 `ULONG32`끝 오프셋을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="afa29-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afa29-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="afa29-107">Return Value</span></span>  
 <span data-ttu-id="afa29-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="afa29-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa29-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afa29-109">Requirements</span></span>  
 <span data-ttu-id="afa29-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="afa29-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa29-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afa29-111">See also</span></span>

- [<span data-ttu-id="afa29-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afa29-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="afa29-113">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="afa29-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
