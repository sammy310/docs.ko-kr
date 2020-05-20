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
ms.openlocfilehash: 543bd208e5492460435663c32f276472a763f613
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441099"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="cdb91-102">ISymUnmanagedDocument::GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="cdb91-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="cdb91-103">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdb91-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb91-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdb91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdb91-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdb91-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="cdb91-106">진행 매개 변수에서 제공 하는 버퍼의 길이입니다. `data`</span><span class="sxs-lookup"><span data-stu-id="cdb91-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="cdb91-107">제한이 체크섬의 크기 및 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb91-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="cdb91-108">제한이 체크섬을 수신 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb91-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdb91-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="cdb91-109">Return Value</span></span>  
 <span data-ttu-id="cdb91-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cdb91-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb91-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdb91-111">See also</span></span>

- [<span data-ttu-id="cdb91-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdb91-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
