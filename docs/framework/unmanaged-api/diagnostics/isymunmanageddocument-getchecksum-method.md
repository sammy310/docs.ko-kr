---
title: ISymUnmanagedDocument::GetCheckSum 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a60bf279c143559e7410d8dfd8213d3da1d05a6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127564"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="1ce43-102">ISymUnmanagedDocument::GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="1ce43-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="1ce43-103">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ce43-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce43-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ce43-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce43-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce43-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="1ce43-106">[in] 제공 하는 버퍼의 길이 `data` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce43-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="1ce43-107">[out] 크기와 체크섬, 바이트의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce43-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="1ce43-108">[out] 체크섬을 수신 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce43-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ce43-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ce43-109">Return Value</span></span>  
 <span data-ttu-id="1ce43-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce43-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce43-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ce43-111">See also</span></span>

- [<span data-ttu-id="1ce43-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce43-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
