---
title: ISymUnmanagedWriter::CloseNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: 13a433157e0c92653edf234f1f1f885270196ffd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686412"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="49155-102">ISymUnmanagedWriter::CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="49155-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>

<span data-ttu-id="49155-103">가장 최근에 열린 네임 스페이스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="49155-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49155-104">구문</span><span class="sxs-lookup"><span data-stu-id="49155-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="49155-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="49155-105">Return Value</span></span>  

 <span data-ttu-id="49155-106">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="49155-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49155-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49155-107">Requirements</span></span>  

 <span data-ttu-id="49155-108">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="49155-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49155-109">참조</span><span class="sxs-lookup"><span data-stu-id="49155-109">See also</span></span>

- [<span data-ttu-id="49155-110">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49155-110">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="49155-111">OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="49155-111">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
