---
description: '자세히 알아보기: ISymUnmanagedReader2:: GetSymAttributePreRemap 메서드'
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
ms.openlocfilehash: 843a3d2d2a568fdff83d2e416fff426daad14645
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763633"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="2aa67-103">ISymUnmanagedReader2::GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="2aa67-103">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>

<span data-ttu-id="2aa67-104">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-104">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="2aa67-105">메타 데이터 사용자 지정 특성과 달리 이러한 특성은 기호 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-105">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa67-106">구문</span><span class="sxs-lookup"><span data-stu-id="2aa67-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aa67-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2aa67-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="2aa67-108">진행 부모의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-108">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="2aa67-109">진행 이름을 포함 하는에 대 한 포인터입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="2aa67-109">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="2aa67-110">진행 `ULONG32` 배열의 크기를 나타내는입니다 `buffer` .</span><span class="sxs-lookup"><span data-stu-id="2aa67-110">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="2aa67-111">제한이 `ULONG32` 특성 바이트를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-111">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2aa67-112">제한이 특성 바이트를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-112">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2aa67-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="2aa67-113">Return Value</span></span>  

 <span data-ttu-id="2aa67-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2aa67-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa67-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2aa67-115">Requirements</span></span>  

 <span data-ttu-id="2aa67-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2aa67-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa67-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2aa67-117">See also</span></span>

- [<span data-ttu-id="2aa67-118">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2aa67-118">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
