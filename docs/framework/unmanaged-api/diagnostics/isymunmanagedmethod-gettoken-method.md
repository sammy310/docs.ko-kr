---
title: ISymUnmanagedMethod::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 0803f0b55f19b779f5b6608a9f8200d2b085b504
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615159"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="46f99-102">ISymUnmanagedMethod::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="46f99-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="46f99-103">이 메서드에 대한 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="46f99-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f99-104">구문</span><span class="sxs-lookup"><span data-stu-id="46f99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46f99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46f99-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="46f99-106">제한이 `mdMethodDef`메타 데이터를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46f99-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46f99-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="46f99-107">Return Value</span></span>  
 <span data-ttu-id="46f99-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="46f99-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f99-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46f99-109">Requirements</span></span>  
 <span data-ttu-id="46f99-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="46f99-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f99-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46f99-111">See also</span></span>

- [<span data-ttu-id="46f99-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46f99-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
