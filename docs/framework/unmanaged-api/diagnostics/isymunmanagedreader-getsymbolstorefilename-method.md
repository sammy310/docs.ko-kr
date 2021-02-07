---
description: '자세히 알아보기: ISymUnmanagedReader:: Get기호 파일 이름 메서드'
title: ISymUnmanagedReader::GetSymbolStoreFileName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: 5cbb33a39cf2e93eab64d5f1f1fefc5ceba1d418
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763945"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="e6ce8-103">ISymUnmanagedReader::GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="e6ce8-103">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>

<span data-ttu-id="e6ce8-104">기호 저장소의 디스크에 있는 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ce8-104">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6ce8-105">구문</span><span class="sxs-lookup"><span data-stu-id="e6ce8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6ce8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e6ce8-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="e6ce8-107">진행 버퍼의 크기 `szName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e6ce8-107">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e6ce8-108">제한이 Null 종료를 포함 하 여에서 반환 되는 이름의 길이를 받는 변수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="e6ce8-108">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="e6ce8-109">제한이 기호 저장소의 파일 이름을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e6ce8-109">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6ce8-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="e6ce8-110">Return Value</span></span>  

 <span data-ttu-id="e6ce8-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e6ce8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6ce8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6ce8-112">Requirements</span></span>  

 <span data-ttu-id="e6ce8-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="e6ce8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ce8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6ce8-114">See also</span></span>

- [<span data-ttu-id="e6ce8-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6ce8-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
