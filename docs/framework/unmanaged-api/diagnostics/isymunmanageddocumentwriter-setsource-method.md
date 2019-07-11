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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 555926e0e6a669f70bdeff484cff0eb62ae11f7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776934"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="c4e29-102">ISymUnmanagedDocumentWriter::SetSource 메서드</span><span class="sxs-lookup"><span data-stu-id="c4e29-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="c4e29-103">포함 된 기록 되는 문서에 대 한 소스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e29-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e29-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4e29-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4e29-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="c4e29-106">[in] A `ULONG32` 의 크기를 포함 하는 `source` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e29-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="c4e29-107">[in] 포함된 된 소스를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e29-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4e29-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c4e29-108">Return Value</span></span>  
 <span data-ttu-id="c4e29-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e29-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e29-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4e29-110">Requirements</span></span>  
 <span data-ttu-id="c4e29-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c4e29-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e29-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4e29-112">See also</span></span>

- [<span data-ttu-id="c4e29-113">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4e29-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
