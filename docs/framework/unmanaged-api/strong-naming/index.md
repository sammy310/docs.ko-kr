---
description: '자세한 정보: 강력한 이름 지정(관리되지 않는 API 참조)'
title: 강력한 이름 지정(관리되지 않는 API 참조)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 058cc51d8e9eb2ef4a2d0670811aefcd32dafb6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646363"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="9c888-103">강력한 이름 지정(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="9c888-103">Strong Naming (Unmanaged API Reference)</span></span>

<span data-ttu-id="9c888-104">강력한 이름 API를 통해 클라이언트는 어셈블리에 대한 강력한 이름 서명을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-104">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="9c888-105">강력한 이름을 사용하여 어셈블리에 서명하면 어셈블리 매니페스트를 포함하는 파일에 공개 키 암호화가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-105">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="9c888-106">강력한 이름 서명은 참조가 해결될 때 이름의 고유성을 확인하고, 이름 스푸핑을 방지하며, 호출자에게 고유한 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-106">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="9c888-107">그러나 강력한 이름과 관련된 신뢰 수준이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-107">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c888-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9c888-108">In This Section</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c888-109">이러한 모든 함수는 .NET Framework 4부터는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-109">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="9c888-110">권장된 대안은 [ICLRStrongName](../hosting/iclrstrongname-interface.md) 인터페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c888-110">For suggested alternatives, see the [ICLRStrongName](../hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="9c888-111">GetHashFromAssemblyFile 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-111">GetHashFromAssemblyFile Function</span></span>](gethashfromassemblyfile-function.md)  
 <span data-ttu-id="9c888-112">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-112">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="9c888-113">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-113">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-114">GetHashFromAssemblyFileW 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-114">GetHashFromAssemblyFileW Function</span></span>](gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="9c888-115">지정된 해시 알고리즘을 사용하여 유니코드 문자열로 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-115">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="9c888-116">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-116">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-117">GetHashFromBlob 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-117">GetHashFromBlob Function</span></span>](gethashfromblob-function.md)  
 <span data-ttu-id="9c888-118">지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-118">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="9c888-119">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-119">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-120">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-120">GetHashFromFile Function</span></span>](gethashfromfile-function.md)  
 <span data-ttu-id="9c888-121">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-121">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="9c888-122">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-122">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-123">GetHashFromFileW 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-123">GetHashFromFileW Function</span></span>](gethashfromfilew-function.md)  
 <span data-ttu-id="9c888-124">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-124">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="9c888-125">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-125">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-126">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-126">GetHashFromHandle Function</span></span>](gethashfromhandle-function.md)  
 <span data-ttu-id="9c888-127">지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-127">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="9c888-128">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-128">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-129">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-129">StrongNameCompareAssemblies Function</span></span>](strongnamecompareassemblies-function.md)  
 <span data-ttu-id="9c888-130">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-130">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="9c888-131">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-131">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-132">StrongNameErrorInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-132">StrongNameErrorInfo Function</span></span>](strongnameerrorinfo-function.md)  
 <span data-ttu-id="9c888-133">강력한 이름 함수 중 하나에 의해 발생하는 마지막 오류 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-133">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="9c888-134">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-134">StrongNameFreeBuffer Function</span></span>](strongnamefreebuffer-function.md)  
 <span data-ttu-id="9c888-135">[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-135">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="9c888-136">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-136">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-137">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-137">StrongNameGetBlob Function</span></span>](strongnamegetblob-function.md)  
 <span data-ttu-id="9c888-138">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-138">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="9c888-139">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-139">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-140">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-140">StrongNameGetBlobFromImage Function</span></span>](strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="9c888-141">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-141">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="9c888-142">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-142">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-143">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-143">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)  
 <span data-ttu-id="9c888-144">퍼블릭/퍼블릭 키 쌍에서 퍼블릭 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-144">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="9c888-145">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-145">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-146">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-146">StrongNameHashSize Function</span></span>](strongnamehashsize-function.md)  
 <span data-ttu-id="9c888-147">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-147">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="9c888-148">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-148">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-149">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-149">StrongNameKeyDelete Function</span></span>](strongnamekeydelete-function.md)  
 <span data-ttu-id="9c888-150">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-150">Deletes the specified key container.</span></span> <span data-ttu-id="9c888-151">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-151">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-152">StrongNameKeyGen 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-152">StrongNameKeyGen Function</span></span>](strongnamekeygen-function.md)  
 <span data-ttu-id="9c888-153">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-153">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="9c888-154">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-154">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-155">StrongNameKeyGenEx 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-155">StrongNameKeyGenEx Function</span></span>](strongnamekeygenex-function.md)  
 <span data-ttu-id="9c888-156">강력한 이름 사용을 위해 지정된 키 크기로 새 퍼블릭/프라이빗 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-156">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="9c888-157">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-157">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-158">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-158">StrongNameKeyInstall Function</span></span>](strongnamekeyinstall-function.md)  
 <span data-ttu-id="9c888-159">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-159">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="9c888-160">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-160">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-161">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-161">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="9c888-162">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-162">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="9c888-163">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-163">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-164">StrongNameSignatureGenerationEx 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-164">StrongNameSignatureGenerationEx Function</span></span>](strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="9c888-165">지정된 플래그에 따라 지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-165">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="9c888-166">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-166">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-167">StrongNameSignatureSize 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-167">StrongNameSignatureSize Function</span></span>](strongnamesignaturesize-function.md)  
 <span data-ttu-id="9c888-168">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-168">Returns the size of the strong name signature.</span></span> <span data-ttu-id="9c888-169">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-169">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-170">StrongNameSignatureVerification 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-170">StrongNameSignatureVerification Function</span></span>](strongnamesignatureverification-function.md)  
 <span data-ttu-id="9c888-171">제공된 경로의 어셈블리 매니페스트에 지정된 플래그에 따라 확인되는 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-171">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="9c888-172">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-172">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-173">StrongNameSignatureVerificationEx 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-173">StrongNameSignatureVerificationEx Function</span></span>](strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="9c888-174">제공된 경로의 어셈블리 매니페스트에 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-174">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="9c888-175">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-175">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-176">StrongNameSignatureVerificationFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-176">StrongNameSignatureVerificationFromImage Function</span></span>](strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="9c888-177">메모리에 이미 매핑된 어셈블리가 연결된 공개 키에 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-177">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="9c888-178">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-178">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-179">StrongNameTokenFromAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-179">StrongNameTokenFromAssembly Function</span></span>](strongnametokenfromassembly-function.md)  
 <span data-ttu-id="9c888-180">지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-180">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="9c888-181">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-181">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-182">StrongNameTokenFromAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-182">StrongNameTokenFromAssemblyEx Function</span></span>](strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="9c888-183">지정된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-183">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="9c888-184">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-184">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-185">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="9c888-185">StrongNameTokenFromPublicKey Function</span></span>](strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="9c888-186">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-186">Gets a token representing a public key.</span></span> <span data-ttu-id="9c888-187">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-187">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="9c888-188">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="9c888-188">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)  
 <span data-ttu-id="9c888-189">퍼블릭/프라이빗 키 쌍의 퍼블릭 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c888-189">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c888-190">참조</span><span class="sxs-lookup"><span data-stu-id="9c888-190">See also</span></span>

- [<span data-ttu-id="9c888-191">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c888-191">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="9c888-192">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="9c888-192">Unmanaged API Reference</span></span>](../index.md)
