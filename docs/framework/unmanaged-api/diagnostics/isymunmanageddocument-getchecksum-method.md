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
ms.openlocfilehash: 52e1fc20fbe1d8709c21cacde926cf8bebb49425
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449208"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="f6906-102">ISymUnmanagedDocument::GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="f6906-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="f6906-103">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6906-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6906-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6906-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6906-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6906-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="f6906-106">진행 `data` 매개 변수에서 제공 하는 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="f6906-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="f6906-107">제한이 체크섬의 크기 및 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6906-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="f6906-108">제한이 체크섬을 수신 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f6906-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6906-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="f6906-109">Return Value</span></span>  
 <span data-ttu-id="f6906-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f6906-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6906-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6906-111">See also</span></span>

- [<span data-ttu-id="f6906-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6906-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
