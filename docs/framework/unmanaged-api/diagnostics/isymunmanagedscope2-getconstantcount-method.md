---
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
ms.openlocfilehash: 88fc6b7d6076bca42050ca87533062557e6a7b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610953"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="17189-102">ISymUnmanagedScope2::GetConstantCount 메서드</span><span class="sxs-lookup"><span data-stu-id="17189-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="17189-103">이 범위 내에 정의 된 상수의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17189-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17189-104">구문</span><span class="sxs-lookup"><span data-stu-id="17189-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17189-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17189-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="17189-106">제한이 `ULONG32`상수를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="17189-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17189-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="17189-107">Return Value</span></span>  
 <span data-ttu-id="17189-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="17189-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17189-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17189-109">Requirements</span></span>  
 <span data-ttu-id="17189-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="17189-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17189-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17189-111">See also</span></span>

- [<span data-ttu-id="17189-112">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17189-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
