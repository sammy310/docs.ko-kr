---
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
ms.openlocfilehash: 3f0d0e060bba832080dd8fbfab62f3115fec0aab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689643"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="3b35b-102">ISymUnmanagedReader::GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="3b35b-102">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="3b35b-103">메서드 토큰이 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b35b-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b35b-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b35b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b35b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b35b-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="3b35b-106">진행 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3b35b-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3b35b-107">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3b35b-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b35b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3b35b-108">Return Value</span></span>  

 <span data-ttu-id="3b35b-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3b35b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b35b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b35b-110">Requirements</span></span>  

 <span data-ttu-id="3b35b-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3b35b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b35b-112">참조</span><span class="sxs-lookup"><span data-stu-id="3b35b-112">See also</span></span>

- [<span data-ttu-id="3b35b-113">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b35b-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
