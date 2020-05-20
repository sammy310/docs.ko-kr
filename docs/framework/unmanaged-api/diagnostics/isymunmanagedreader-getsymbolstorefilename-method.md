---
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
ms.openlocfilehash: 6ffab3b2f81680404f870cfd63ae5125173a346c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615516"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="7ddbd-102">ISymUnmanagedReader::GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="7ddbd-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="7ddbd-103">기호 저장소의 디스크에 있는 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddbd-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddbd-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ddbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ddbd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ddbd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7ddbd-106">진행 버퍼의 크기 `szName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7ddbd-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7ddbd-107">제한이 Null 종료를 포함 하 여에서 반환 되는 이름의 길이를 받는 변수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="7ddbd-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="7ddbd-108">제한이 기호 저장소의 파일 이름을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ddbd-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ddbd-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="7ddbd-109">Return Value</span></span>  
 <span data-ttu-id="7ddbd-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7ddbd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ddbd-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ddbd-111">Requirements</span></span>  
 <span data-ttu-id="7ddbd-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7ddbd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddbd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ddbd-113">See also</span></span>

- [<span data-ttu-id="7ddbd-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ddbd-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
