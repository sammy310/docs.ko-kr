---
title: ISymUnmanagedDocument::HasEmbeddedSource 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 533d8a5481fe9ba7e7e65775229156a9cc3cf4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449116"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="7dfa4-102">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="7dfa4-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="7dfa4-103">문서에 디버깅 기호에 포함 된 소스가 있는 경우 `true`을 반환 합니다. 그렇지 않으면 `false`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa4-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfa4-104">구문</span><span class="sxs-lookup"><span data-stu-id="7dfa4-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dfa4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7dfa4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7dfa4-106">제한이 문서에 디버깅 기호에 포함 된 소스가 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa4-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dfa4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7dfa4-107">Return Value</span></span>  
 <span data-ttu-id="7dfa4-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dfa4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfa4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dfa4-109">See also</span></span>

- [<span data-ttu-id="7dfa4-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7dfa4-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
