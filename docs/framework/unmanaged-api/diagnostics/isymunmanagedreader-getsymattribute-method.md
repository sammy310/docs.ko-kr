---
title: ISymUnmanagedReader::GetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26458e2512f331ff7a8c41868c99d092cfd30977
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737242"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="91786-102">ISymUnmanagedReader::GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="91786-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="91786-103">해당 이름을 기준으로 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91786-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="91786-104">사용자 지정 특성 메타 데이터와 달리 이러한 사용자 지정 특성 기호 저장소에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91786-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91786-105">구문</span><span class="sxs-lookup"><span data-stu-id="91786-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91786-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91786-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="91786-107">[in] 특성이 요청 된 개체에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="91786-108">[in] 검색할 특성을 나타내는 변수의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="91786-109">[in] `buffer` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="91786-110">[out] 특성 데이터의 길이 받는 변수의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="91786-111">[out] 특성 데이터를 받는 변수의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91786-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="91786-112">Return Value</span></span>  
 <span data-ttu-id="91786-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="91786-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91786-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91786-114">Requirements</span></span>  
 <span data-ttu-id="91786-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91786-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91786-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="91786-116">See also</span></span>

- [<span data-ttu-id="91786-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91786-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
