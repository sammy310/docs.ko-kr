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
ms.openlocfilehash: 459a24e2ed9b97a67dc0266231fdfc32a9c853a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776656"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="ab766-102">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="ab766-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="ab766-103">반환 `true` 문서에 소스가 디버깅 기호;에 포함 되어 있으면 반환이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab766-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab766-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab766-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab766-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab766-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ab766-106">[out] 문서에 디버깅 기호를 포함 하는 원본에 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab766-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab766-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab766-107">Return Value</span></span>  
 <span data-ttu-id="ab766-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="ab766-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab766-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab766-109">See also</span></span>

- [<span data-ttu-id="ab766-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab766-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
