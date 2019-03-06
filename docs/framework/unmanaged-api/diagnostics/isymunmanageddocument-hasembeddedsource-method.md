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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 620d303bcd33a4d04155850ec2c1b6293bf788d1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493260"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="0242d-102">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="0242d-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="0242d-103">반환 `true` 문서에 소스가 디버깅 기호;에 포함 되어 있으면 반환이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0242d-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0242d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0242d-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0242d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0242d-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0242d-106">[out] 문서에 디버깅 기호를 포함 하는 원본에 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0242d-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0242d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0242d-107">Return Value</span></span>  
 <span data-ttu-id="0242d-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="0242d-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0242d-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0242d-109">See also</span></span>
- [<span data-ttu-id="0242d-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0242d-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
