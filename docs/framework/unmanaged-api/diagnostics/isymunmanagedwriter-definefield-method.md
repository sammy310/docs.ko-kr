---
title: ISymUnmanagedWriter::DefineField 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: 5683c10938873821cbe998dbf13937a6a7d24d7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675089"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="2ed63-102">ISymUnmanagedWriter::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="2ed63-102">ISymUnmanagedWriter::DefineField Method</span></span>

<span data-ttu-id="2ed63-103">메서드 내에 없는 단일 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="2ed63-104">이 메서드는 클래스, 비트 필드 등의 특정 필드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed63-105">구문</span><span class="sxs-lookup"><span data-stu-id="2ed63-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ed63-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="2ed63-107">진행 메타 데이터 형식 또는 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="2ed63-108">진행 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="2ed63-109">진행 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="2ed63-110">진행 `ULONG32` 필드 시그니처를 포함 하는 데 필요한 버퍼의 크기 (문자 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="2ed63-111">진행 필드 시그니처의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="2ed63-112">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="2ed63-113">진행 필드 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="2ed63-114">진행 필드 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="2ed63-115">진행 필드 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed63-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="2ed63-116">Return Value</span></span>  

 <span data-ttu-id="2ed63-117">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2ed63-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed63-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ed63-118">Requirements</span></span>  

 <span data-ttu-id="2ed63-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2ed63-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed63-120">참조</span><span class="sxs-lookup"><span data-stu-id="2ed63-120">See also</span></span>

- [<span data-ttu-id="2ed63-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ed63-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
