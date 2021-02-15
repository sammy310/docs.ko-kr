---
description: '자세한 정보: 연습: Visual Basic에서 문자열 암호화 및 암호 해독'
title: 문자열 암호화 및 해독
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: afc1eeaec85b2e430aead7f16401289b6e2e9e49
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471086"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="9679e-103">연습: Visual Basic에서 문자열 암호화 및 암호 해독</span><span class="sxs-lookup"><span data-stu-id="9679e-103">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>

<span data-ttu-id="9679e-104">이 연습에서는 클래스를 사용 하 여 <xref:System.Security.Cryptography.DESCryptoServiceProvider> 삼중 데이터 암호화 표준 () 알고리즘의 CSP (암호화 서비스 공급자) 버전을 사용 하 여 문자열을 암호화 하 고 해독 하는 방법을 보여 줍니다 <xref:System.Security.Cryptography.TripleDES> .</span><span class="sxs-lookup"><span data-stu-id="9679e-104">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="9679e-105">첫 번째 단계는 3DES 알고리즘을 캡슐화 하 고 암호화 된 데이터를 base-64로 인코딩된 문자열로 저장 하는 간단한 래퍼 클래스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-105">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="9679e-106">그런 다음이 래퍼는 공개적으로 액세스할 수 있는 텍스트 파일에 개인 사용자 데이터를 안전 하 게 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-106">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="9679e-107">암호화를 사용 하 여 사용자 비밀 (예: 암호)을 보호 하 고 권한이 없는 사용자가 자격 증명을 읽을 수 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-107">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="9679e-108">이렇게 하면 권한 있는 사용자의 id가 도난당 하지 않도록 보호할 수 있으므로 사용자의 자산을 보호 하 고 부인 방지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-108">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="9679e-109">암호화는 권한이 없는 사용자가 액세스 하는 사용자의 데이터를 보호할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-109">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="9679e-110">자세한 내용은 [암호화 서비스](../../../../standard/security/cryptographic-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9679e-110">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9679e-111">Rijndael (현재 AES(Advanced Encryption Standard) [AES] 이라고 함) 및 3DES (Triple Data Encryption Standard) 알고리즘은 더 많은 계산을 많이 하므로 DES 보다 더 높은 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-111">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="9679e-112">자세한 내용은 <xref:System.Security.Cryptography.DES> 및 <xref:System.Security.Cryptography.Rijndael>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9679e-112">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="9679e-113">암호화 래퍼를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9679e-113">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="9679e-114">`Simple3Des`암호화 및 암호 해독 메서드를 캡슐화 하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-114">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="9679e-115">암호화 네임 스페이스의 가져오기를 클래스를 포함 하는 파일의 시작 부분에 추가 합니다 `Simple3Des` .</span><span class="sxs-lookup"><span data-stu-id="9679e-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="9679e-116">클래스에서 `Simple3Des` 3des 암호화 서비스 공급자를 저장할 전용 필드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-116">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="9679e-117">지정 된 키의 해시에서 지정 된 길이의 바이트 배열을 만드는 전용 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-117">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="9679e-118">3DES 암호화 서비스 공급자를 초기화 하는 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-118">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="9679e-119">`key`매개 변수는 및 메서드를 제어 합니다 `EncryptData` `DecryptData` .</span><span class="sxs-lookup"><span data-stu-id="9679e-119">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="9679e-120">문자열을 암호화 하는 공용 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-120">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="9679e-121">문자열을 해독 하는 공용 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-121">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="9679e-122">이제 래퍼 클래스를 사용 하 여 사용자 자산을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-122">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="9679e-123">이 예제에서는 공개적으로 액세스할 수 있는 텍스트 파일에 개인 사용자 데이터를 안전 하 게 저장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-123">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="9679e-124">암호화 래퍼를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="9679e-124">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="9679e-125">별도의 클래스에서 래퍼 메서드를 사용 하 여 `EncryptData` 문자열을 암호화 하 고 사용자의 내 문서 폴더에 쓰는 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-125">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="9679e-126">사용자의 내 문서 폴더에서 암호화 된 문자열을 읽고 래퍼 메서드를 사용 하 여 문자열의 암호를 해독 하는 메서드를 추가 `DecryptData` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-126">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="9679e-127">및 메서드를 호출 하는 사용자 인터페이스 코드를 추가 `TestEncoding` `TestDecoding` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-127">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="9679e-128">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-128">Run the application.</span></span>  
  
     <span data-ttu-id="9679e-129">응용 프로그램을 테스트할 때 잘못 된 암호를 입력 하면 데이터의 암호를 해독 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9679e-129">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9679e-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9679e-130">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="9679e-131">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="9679e-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
