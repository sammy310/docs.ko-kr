---
title: ISymUnmanagedDocumentWriter::SetSource 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 31475b08b569b925aab9cab869545f0912c4ecf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691593"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="8ee4f-102">ISymUnmanagedDocumentWriter::SetSource 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee4f-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="8ee4f-103">작성 되는 문서에 대해 포함 된 소스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4f-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ee4f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ee4f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ee4f-105">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="8ee4f-106">진행 `ULONG32` 버퍼의 크기를 포함 하는입니다 `source` .</span><span class="sxs-lookup"><span data-stu-id="8ee4f-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="8ee4f-107">진행 포함 된 소스를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4f-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ee4f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="8ee4f-108">Return Value</span></span>  

 <span data-ttu-id="8ee4f-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee4f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee4f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ee4f-110">Requirements</span></span>  

 <span data-ttu-id="8ee4f-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8ee4f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee4f-112">참조</span><span class="sxs-lookup"><span data-stu-id="8ee4f-112">See also</span></span>

- [<span data-ttu-id="8ee4f-113">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ee4f-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
