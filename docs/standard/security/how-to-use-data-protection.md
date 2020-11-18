---
title: '방법: 데이터 보호 사용'
description: .NET에서 DPAPI (데이터 보호 API)에 액세스 하 여 데이터 보호를 사용 하는 방법에 대해 알아봅니다.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: ed1b18e2c6456b53559e8fb7e989f148fefd35c7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820100"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="5bddb-103">방법: 데이터 보호 사용</span><span class="sxs-lookup"><span data-stu-id="5bddb-103">How to: Use Data Protection</span></span>

> [!NOTE]
> <span data-ttu-id="5bddb-104">이 문서는 Windows에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="5bddb-105">ASP.NET Core에 대 한 자세한 내용은 [데이터 보호 ASP.NET Core](/aspnet/core/security/data-protection/introduction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5bddb-105">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="5bddb-106">.NET에서는 DPAPI (데이터 보호 API)에 대 한 액세스를 제공 하므로 현재 사용자 계정 또는 컴퓨터의 정보를 사용 하 여 데이터를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-106">.NET provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="5bddb-107">DPAPI를 사용하는 경우 명시적으로 암호화 키를 생성 및 저장하는 어려운 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-107">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
<span data-ttu-id="5bddb-108"><xref:System.Security.Cryptography.ProtectedData> 클래스를 사용하여 바이트 배열 복사본을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-108">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="5bddb-109">이 기능은 .NET Framework, .NET Core 및 .NET 5에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-109">This functionality is available in .NET Framework, .NET Core, and .NET 5.</span></span>  <span data-ttu-id="5bddb-110">현재 사용자 계정에서 암호화된 데이터가 동일한 사용자 계정에 의해서만 암호 해독될 수 있도록 지정하거나, 현재 사용자 계정에서 암호화된 데이터가 컴퓨터의 모든 계정에 의해 암호 해독될 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-110">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="5bddb-111"><xref:System.Security.Cryptography.ProtectedData> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.DataProtectionScope> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bddb-111">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="5bddb-112">데이터 보호를 사용 하 여 파일 또는 스트림으로 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="5bddb-112">Encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="5bddb-113">임의 엔트로피를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-113">Create random entropy.</span></span>  
  
2. <span data-ttu-id="5bddb-114">암호화할 바이트 배열, 엔트로피 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Protect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-114">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="5bddb-115">파일 또는 스트림에 암호화된 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-115">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="5bddb-116">데이터 보호를 사용하여 파일 또는 스트림에서 데이터를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="5bddb-116">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="5bddb-117">파일 또는 스트림에서 암호화된 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-117">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="5bddb-118">암호 해독할 바이트 배열 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-118">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bddb-119">예제</span><span class="sxs-lookup"><span data-stu-id="5bddb-119">Example</span></span>

<span data-ttu-id="5bddb-120">다음 코드 예제에서는 두 가지 형태의 암호화 및 암호 해독을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-120">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="5bddb-121">먼저 코드 예제에서 메모리 내 바이트 배열을 암호화한 다음 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-121">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="5bddb-122">그런 다음 코드 예제에서 바이트 배열의 복사본을 암호화하고 파일에 저장한 다음 파일에서 다시 데이터를 로드하고 데이터를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-122">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="5bddb-123">이 예제에서는 원본 데이터, 암호화된 데이터 및 암호 해독된 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-123">The example displays the original data, the encrypted data, and the decrypted data.</span></span>

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5bddb-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5bddb-124">Compiling the Code</span></span>  

<span data-ttu-id="5bddb-125">이 예제는 Windows에서 .NET Framework 및 실행을 대상으로 하는 경우에만 컴파일되고 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-125">This example compiles and runs only when targeting .NET Framework and running on Windows.</span></span>

- <span data-ttu-id="5bddb-126">`System.Security.dll`에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-126">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="5bddb-127"><xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> 및 <xref:System.Text> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5bddb-127">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bddb-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bddb-128">See also</span></span>

- [<span data-ttu-id="5bddb-129">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="5bddb-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="5bddb-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="5bddb-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="5bddb-131">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="5bddb-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [<span data-ttu-id="5bddb-132">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="5bddb-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
