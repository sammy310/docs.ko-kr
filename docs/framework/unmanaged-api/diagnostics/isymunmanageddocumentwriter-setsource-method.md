---
description: '자세히 알아보기: ISymUnmanagedDocumentWriter:: SetSource 메서드'
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
ms.openlocfilehash: e24e34a297a9931babf3df4f2bae1b5e8f60db1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721478"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="cfd18-103">ISymUnmanagedDocumentWriter::SetSource 메서드</span><span class="sxs-lookup"><span data-stu-id="cfd18-103">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="cfd18-104">작성 되는 문서에 대해 포함 된 소스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfd18-104">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd18-105">구문</span><span class="sxs-lookup"><span data-stu-id="cfd18-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfd18-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfd18-106">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="cfd18-107">진행 `ULONG32` 버퍼의 크기를 포함 하는입니다 `source` .</span><span class="sxs-lookup"><span data-stu-id="cfd18-107">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="cfd18-108">진행 포함 된 소스를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cfd18-108">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfd18-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="cfd18-109">Return Value</span></span>  

 <span data-ttu-id="cfd18-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cfd18-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd18-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfd18-111">Requirements</span></span>  

 <span data-ttu-id="cfd18-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cfd18-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd18-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfd18-113">See also</span></span>

- [<span data-ttu-id="cfd18-114">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfd18-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
