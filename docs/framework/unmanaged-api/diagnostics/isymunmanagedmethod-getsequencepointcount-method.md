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
ms.openlocfilehash: 44472c7beff72d24853b7fb9865071a9b15ef0e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699432"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="7b8ea-102">ISymUnmanagedMethod::GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="7b8ea-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>

<span data-ttu-id="7b8ea-103">이 메서드 내의 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="7b8ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b8ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b8ea-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="7b8ea-106">제한이 `ULONG32` 시퀀스 위치를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b8ea-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7b8ea-107">Return Value</span></span>  

 <span data-ttu-id="7b8ea-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8ea-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b8ea-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b8ea-109">Requirements</span></span>  

 <span data-ttu-id="7b8ea-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7b8ea-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8ea-111">참조</span><span class="sxs-lookup"><span data-stu-id="7b8ea-111">See also</span></span>

- [<span data-ttu-id="7b8ea-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b8ea-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
