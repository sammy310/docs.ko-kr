---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: 393984241412f543b6ac082484cf5e23edb2d9f4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448988"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="dc680-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드</span><span class="sxs-lookup"><span data-stu-id="dc680-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="dc680-103">줄 정보가 요구 사항을 충족 하는 경우 컴파일러가 PDB (프로그램 데이터베이스) 스트림에서 수정 되지 않은 함수를 생략할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="dc680-104">올바른 줄 정보는 이전 PDB 줄 정보와 함수의 모든 줄에 대해 델타 하나를 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc680-105">구문</span><span class="sxs-lookup"><span data-stu-id="dc680-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc680-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc680-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="dc680-107">진행 줄 정보가 포함 된 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="dc680-108">진행 변경 된 줄을 포함 하는 [Symlinedelta](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="dc680-109">진행 변경 된 줄 수를 나타내는 `ULONG`입니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc680-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc680-110">Return Value</span></span>  
 <span data-ttu-id="dc680-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="dc680-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc680-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc680-112">Requirements</span></span>  
 <span data-ttu-id="dc680-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="dc680-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc680-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc680-114">See also</span></span>

- [<span data-ttu-id="dc680-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc680-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
