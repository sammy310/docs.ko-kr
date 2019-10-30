---
title: 강력한 이름 지정(관리되지 않는 API 참조)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7d18513450111d58b5d26fd834addd465cfc4267
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140641"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="5a00b-102">강력한 이름 지정(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5a00b-102">Strong Naming (Unmanaged API Reference)</span></span>
<span data-ttu-id="5a00b-103">강력한 이름 API를 통해 클라이언트는 어셈블리에 대한 강력한 이름 서명을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="5a00b-104">강력한 이름을 사용하여 어셈블리에 서명하면 어셈블리 매니페스트를 포함하는 파일에 공개 키 암호화가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="5a00b-105">강력한 이름 서명은 참조가 해결될 때 이름의 고유성을 확인하고, 이름 스푸핑을 방지하며, 호출자에게 고유한 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="5a00b-106">그러나 강력한 이름과 관련된 신뢰 수준이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a00b-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5a00b-107">In This Section</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a00b-108">이러한 모든 함수는 .NET Framework 4부터는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-108">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="5a00b-109">권장된 대안은 [ICLRStrongName](../hosting/iclrstrongname-interface.md) 인터페이스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a00b-109">For suggested alternatives, see the [ICLRStrongName](../hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="5a00b-110">GetHashFromAssemblyFile 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-110">GetHashFromAssemblyFile Function</span></span>](gethashfromassemblyfile-function.md)  
 <span data-ttu-id="5a00b-111">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="5a00b-112">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-113">GetHashFromAssemblyFileW 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-113">GetHashFromAssemblyFileW Function</span></span>](gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="5a00b-114">지정된 해시 알고리즘을 사용하여 유니코드 문자열로 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="5a00b-115">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-116">GetHashFromBlob 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-116">GetHashFromBlob Function</span></span>](gethashfromblob-function.md)  
 <span data-ttu-id="5a00b-117">지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="5a00b-118">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-119">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-119">GetHashFromFile Function</span></span>](gethashfromfile-function.md)  
 <span data-ttu-id="5a00b-120">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="5a00b-121">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-122">GetHashFromFileW 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-122">GetHashFromFileW Function</span></span>](gethashfromfilew-function.md)  
 <span data-ttu-id="5a00b-123">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="5a00b-124">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-125">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-125">GetHashFromHandle Function</span></span>](gethashfromhandle-function.md)  
 <span data-ttu-id="5a00b-126">지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="5a00b-127">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-128">StrongNameCompareAssemblies 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-128">StrongNameCompareAssemblies Function</span></span>](strongnamecompareassemblies-function.md)  
 <span data-ttu-id="5a00b-129">두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="5a00b-130">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-131">StrongNameErrorInfo 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-131">StrongNameErrorInfo Function</span></span>](strongnameerrorinfo-function.md)  
 <span data-ttu-id="5a00b-132">강력한 이름 함수 중 하나에 의해 발생하는 마지막 오류 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="5a00b-133">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-133">StrongNameFreeBuffer Function</span></span>](strongnamefreebuffer-function.md)  
 <span data-ttu-id="5a00b-134">[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="5a00b-135">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-136">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-136">StrongNameGetBlob Function</span></span>](strongnamegetblob-function.md)  
 <span data-ttu-id="5a00b-137">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="5a00b-138">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-139">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-139">StrongNameGetBlobFromImage Function</span></span>](strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="5a00b-140">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="5a00b-141">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-142">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-142">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)  
 <span data-ttu-id="5a00b-143">퍼블릭/퍼블릭 키 쌍에서 퍼블릭 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="5a00b-144">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-145">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-145">StrongNameHashSize Function</span></span>](strongnamehashsize-function.md)  
 <span data-ttu-id="5a00b-146">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="5a00b-147">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-148">StrongNameKeyDelete 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-148">StrongNameKeyDelete Function</span></span>](strongnamekeydelete-function.md)  
 <span data-ttu-id="5a00b-149">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-149">Deletes the specified key container.</span></span> <span data-ttu-id="5a00b-150">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-151">StrongNameKeyGen 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-151">StrongNameKeyGen Function</span></span>](strongnamekeygen-function.md)  
 <span data-ttu-id="5a00b-152">강력한 이름 사용을 위한 새 퍼블릭/프라이빗 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="5a00b-153">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-154">StrongNameKeyGenEx 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-154">StrongNameKeyGenEx Function</span></span>](strongnamekeygenex-function.md)  
 <span data-ttu-id="5a00b-155">강력한 이름 사용을 위해 지정된 키 크기로 새 퍼블릭/프라이빗 키 쌍을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="5a00b-156">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-157">StrongNameKeyInstall 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-157">StrongNameKeyInstall Function</span></span>](strongnamekeyinstall-function.md)  
 <span data-ttu-id="5a00b-158">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="5a00b-159">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-160">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-160">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="5a00b-161">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="5a00b-162">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-163">StrongNameSignatureGenerationEx 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-163">StrongNameSignatureGenerationEx Function</span></span>](strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="5a00b-164">지정된 플래그에 따라 지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="5a00b-165">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-166">StrongNameSignatureSize 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-166">StrongNameSignatureSize Function</span></span>](strongnamesignaturesize-function.md)  
 <span data-ttu-id="5a00b-167">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="5a00b-168">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-169">StrongNameSignatureVerification 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-169">StrongNameSignatureVerification Function</span></span>](strongnamesignatureverification-function.md)  
 <span data-ttu-id="5a00b-170">제공된 경로의 어셈블리 매니페스트에 지정된 플래그에 따라 확인되는 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="5a00b-171">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-172">StrongNameSignatureVerificationEx 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-172">StrongNameSignatureVerificationEx Function</span></span>](strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="5a00b-173">제공된 경로의 어셈블리 매니페스트에 강력한 이름 서명이 포함되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="5a00b-174">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-175">StrongNameSignatureVerificationFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-175">StrongNameSignatureVerificationFromImage Function</span></span>](strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="5a00b-176">메모리에 이미 매핑된 어셈블리가 연결된 공개 키에 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="5a00b-177">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-178">StrongNameTokenFromAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-178">StrongNameTokenFromAssembly Function</span></span>](strongnametokenfromassembly-function.md)  
 <span data-ttu-id="5a00b-179">지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="5a00b-180">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-181">StrongNameTokenFromAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-181">StrongNameTokenFromAssemblyEx Function</span></span>](strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="5a00b-182">지정된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="5a00b-183">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-184">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="5a00b-184">StrongNameTokenFromPublicKey Function</span></span>](strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="5a00b-185">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-185">Gets a token representing a public key.</span></span> <span data-ttu-id="5a00b-186">.NET Framework 4부터 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="5a00b-187">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="5a00b-187">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)  
 <span data-ttu-id="5a00b-188">퍼블릭/프라이빗 키 쌍의 퍼블릭 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a00b-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a00b-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a00b-189">See also</span></span>

- [<span data-ttu-id="5a00b-190">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a00b-190">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="5a00b-191">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="5a00b-191">Unmanaged API Reference</span></span>](../index.md)
