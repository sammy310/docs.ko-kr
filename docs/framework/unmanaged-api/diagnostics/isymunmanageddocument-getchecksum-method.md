---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetCheckSum 메서드'
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
ms.openlocfilehash: 9f9a42e58b22661a2233fcb457b9b42b0d6a3d1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737690"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="950b1-103">ISymUnmanagedDocument::GetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="950b1-103">ISymUnmanagedDocument::GetCheckSum Method</span></span>

<span data-ttu-id="950b1-104">체크섬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="950b1-104">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950b1-105">구문</span><span class="sxs-lookup"><span data-stu-id="950b1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="950b1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="950b1-106">Parameters</span></span>  

 `cData`  
 <span data-ttu-id="950b1-107">진행 매개 변수에서 제공 하는 버퍼의 길이입니다. `data`</span><span class="sxs-lookup"><span data-stu-id="950b1-107">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="950b1-108">제한이 체크섬의 크기 및 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="950b1-108">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="950b1-109">제한이 체크섬을 수신 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="950b1-109">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="950b1-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="950b1-110">Return Value</span></span>  

 <span data-ttu-id="950b1-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="950b1-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950b1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="950b1-112">See also</span></span>

- [<span data-ttu-id="950b1-113">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="950b1-113">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
