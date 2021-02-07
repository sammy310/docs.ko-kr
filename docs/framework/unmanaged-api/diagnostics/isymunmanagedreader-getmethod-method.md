---
description: '자세히 알아보기: ISymUnmanagedReader:: GetMethod 메서드'
title: ISymUnmanagedReader::GetMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 7c0bb65840a3bc1c9450ad29fa8438cdb0377a16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689497"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="a9c77-103">ISymUnmanagedReader::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c77-103">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="a9c77-104">메서드 토큰이 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9c77-104">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c77-105">구문</span><span class="sxs-lookup"><span data-stu-id="a9c77-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c77-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9c77-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="a9c77-107">진행 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c77-107">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a9c77-108">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c77-108">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9c77-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="a9c77-109">Return Value</span></span>  

 <span data-ttu-id="a9c77-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a9c77-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c77-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9c77-111">Requirements</span></span>  

 <span data-ttu-id="a9c77-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a9c77-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c77-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9c77-113">See also</span></span>

- [<span data-ttu-id="a9c77-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c77-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
