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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f8804c911e053758442670afb3c3f27d0f7453
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130054"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="509e3-102">ISymUnmanagedWriter::CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="509e3-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="509e3-103">닫히는 네임 스페이스를 가장 최근에 열립니다.</span><span class="sxs-lookup"><span data-stu-id="509e3-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="509e3-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="509e3-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="509e3-105">Return Value</span></span>  
 <span data-ttu-id="509e3-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="509e3-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509e3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="509e3-107">Requirements</span></span>  
 <span data-ttu-id="509e3-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="509e3-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509e3-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="509e3-109">See also</span></span>

- [<span data-ttu-id="509e3-110">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="509e3-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="509e3-111">OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="509e3-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
