---
title: ISymUnmanagedReader2::GetSymAttributePreRemap 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: e6248aba1c41b2815f2806942d419da869ed94b4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614918"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="e0d1d-102">ISymUnmanagedReader2::GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="e0d1d-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="e0d1d-103">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="e0d1d-104">메타 데이터 사용자 지정 특성과 달리 이러한 특성은 기호 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d1d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e0d1d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0d1d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0d1d-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="e0d1d-107">진행 부모의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="e0d1d-108">진행 이름을 포함 하는에 대 한 포인터입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="e0d1d-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="e0d1d-109">진행 `ULONG32`배열의 크기를 나타내는입니다 `buffer` .</span><span class="sxs-lookup"><span data-stu-id="e0d1d-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="e0d1d-110">제한이 `ULONG32`특성 바이트를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e0d1d-111">제한이 특성 바이트를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0d1d-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="e0d1d-112">Return Value</span></span>  
 <span data-ttu-id="e0d1d-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0d1d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0d1d-114">Requirements</span></span>  
 <span data-ttu-id="e0d1d-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="e0d1d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d1d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0d1d-116">See also</span></span>

- [<span data-ttu-id="e0d1d-117">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0d1d-117">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
