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
ms.openlocfilehash: 7f04b5c100f1fd9c44e671b883fe469b16d33fa6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440143"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="005b9-102">ISymUnmanagedReader::GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="005b9-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="005b9-103">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="005b9-104">메타 데이터 사용자 지정 특성과 달리 이러한 사용자 지정 특성은 기호 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="005b9-105">구문</span><span class="sxs-lookup"><span data-stu-id="005b9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="005b9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="005b9-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="005b9-107">진행 특성이 요청 된 개체에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="005b9-108">진행 검색할 특성을 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="005b9-109">[in] `buffer` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="005b9-110">제한이 특성 데이터의 길이를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="005b9-111">제한이 특성 데이터를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="005b9-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="005b9-112">Return Value</span></span>  
 <span data-ttu-id="005b9-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="005b9-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="005b9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="005b9-114">Requirements</span></span>  
 <span data-ttu-id="005b9-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="005b9-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005b9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="005b9-116">See also</span></span>

- [<span data-ttu-id="005b9-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="005b9-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
