---
title: ISymUnmanagedMethod::GetSequencePointCount 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: a44f81deb2d57b49f1fd0650fa52c06383210352
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614437"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="06b5a-102">ISymUnmanagedMethod::GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="06b5a-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="06b5a-103">이 메서드 내의 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06b5a-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b5a-104">구문</span><span class="sxs-lookup"><span data-stu-id="06b5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b5a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06b5a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="06b5a-106">제한이 `ULONG32`시퀀스 위치를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06b5a-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b5a-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="06b5a-107">Return Value</span></span>  
 <span data-ttu-id="06b5a-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06b5a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b5a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06b5a-109">Requirements</span></span>  
 <span data-ttu-id="06b5a-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="06b5a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b5a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06b5a-111">See also</span></span>

- [<span data-ttu-id="06b5a-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06b5a-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
