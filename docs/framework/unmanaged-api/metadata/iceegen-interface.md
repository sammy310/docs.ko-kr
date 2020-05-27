---
title: ICeeGen 인터페이스
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008276"
---
# <a name="iceegen-interface"></a><span data-ttu-id="e1d1c-102">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1d1c-102">ICeeGen Interface</span></span>
<span data-ttu-id="e1d1c-103">동적 코드 컴파일에 대한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="e1d1c-104">이 인터페이스는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1d1c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-105">Methods</span></span>  
  
|<span data-ttu-id="e1d1c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-106">Method</span></span>|<span data-ttu-id="e1d1c-107">Description</span><span class="sxs-lookup"><span data-stu-id="e1d1c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1d1c-108">AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-108">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="e1d1c-109">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-109">Obsolete.</span></span> <span data-ttu-id="e1d1c-110">코드 베이스에 .reloc 명령을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="e1d1c-111">AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-111">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="e1d1c-112">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-112">Obsolete.</span></span> <span data-ttu-id="e1d1c-113">메서드에 대해 지정 된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="e1d1c-114">ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-114">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="e1d1c-115">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-115">Obsolete.</span></span> <span data-ttu-id="e1d1c-116">지정 된 코드 섹션의 버퍼를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="e1d1c-117">EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-117">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="e1d1c-118">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-118">Obsolete.</span></span> <span data-ttu-id="e1d1c-119">지정 된 문자열을 코드 베이스에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="e1d1c-120">GenerateCeeFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-120">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="e1d1c-121">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-121">Obsolete.</span></span> <span data-ttu-id="e1d1c-122">현재이에 로드 된 코드 베이스를 포함 하는 코드 베이스 파일을 생성 `ICeeGen` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="e1d1c-123">GenerateCeeMemoryImage 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-123">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="e1d1c-124">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-124">Obsolete.</span></span> <span data-ttu-id="e1d1c-125">코드 베이스에 대 한 메모리에 이미지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="e1d1c-126">GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-126">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="e1d1c-127">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-127">Obsolete.</span></span> <span data-ttu-id="e1d1c-128">지정 된 핸들이 참조 하는 중간 언어 코드 베이스의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="e1d1c-129">GetIMapTokenIface 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-129">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="e1d1c-130">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-130">Obsolete.</span></span> <span data-ttu-id="e1d1c-131">지정 된 토큰이 참조 하는 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="e1d1c-132">GetMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-132">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="e1d1c-133">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-133">Obsolete.</span></span> <span data-ttu-id="e1d1c-134">지정 된 상대 가상 주소에서 메서드에 대 한 적절 한 크기의 버퍼를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="e1d1c-135">GetSectionBlock 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-135">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="e1d1c-136">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-136">Obsolete.</span></span> <span data-ttu-id="e1d1c-137">코드 베이스의 섹션 블록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="e1d1c-138">GetSectionCreate 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-138">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="e1d1c-139">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-139">Obsolete.</span></span> <span data-ttu-id="e1d1c-140">지정 된 이름 및 플래그 값을 사용 하 여 코드 섹션을 생성 하 고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="e1d1c-141">GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-141">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="e1d1c-142">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-142">Obsolete.</span></span> <span data-ttu-id="e1d1c-143">지정 된 섹션의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="e1d1c-144">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-144">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="e1d1c-145">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-145">Obsolete.</span></span> <span data-ttu-id="e1d1c-146">지정 된 상대 가상 주소에 저장 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="e1d1c-147">GetStringSection 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-147">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="e1d1c-148">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-148">Obsolete.</span></span> <span data-ttu-id="e1d1c-149">지정 된 핸들이 참조 하는 코드 섹션의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="e1d1c-150">TruncateSection 메서드</span><span class="sxs-lookup"><span data-stu-id="e1d1c-150">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="e1d1c-151">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-151">Obsolete.</span></span> <span data-ttu-id="e1d1c-152">지정 된 코드 섹션을 지정 된 길이로 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1d1c-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1d1c-153">Requirements</span></span>  
 <span data-ttu-id="e1d1c-154">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d1c-155">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e1d1c-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1d1c-156">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1d1c-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1d1c-157">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d1c-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d1c-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1d1c-158">See also</span></span>

- [<span data-ttu-id="e1d1c-159">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1d1c-159">Metadata Interfaces</span></span>](metadata-interfaces.md)
