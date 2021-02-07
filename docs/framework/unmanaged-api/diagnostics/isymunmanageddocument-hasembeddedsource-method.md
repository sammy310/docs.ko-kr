---
description: '자세히 알아보기: ISymUnmanagedDocument:: HasEmbeddedSource 메서드'
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
ms.openlocfilehash: fcab83fea65d9a9e483bff9d2d75714c233718eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710129"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="c34f6-103">ISymUnmanagedDocument::HasEmbeddedSource 메서드</span><span class="sxs-lookup"><span data-stu-id="c34f6-103">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="c34f6-104">`true`문서에 디버깅 기호에 포함 된 소스가 있으면를 반환 하 고, 그렇지 않으면를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34f6-104">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c34f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="c34f6-105">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c34f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c34f6-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="c34f6-107">제한이 문서에 디버깅 기호에 포함 된 소스가 있는지 여부를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c34f6-107">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c34f6-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c34f6-108">Return Value</span></span>  

 <span data-ttu-id="c34f6-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34f6-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34f6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c34f6-110">See also</span></span>

- [<span data-ttu-id="c34f6-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c34f6-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
