---
title: '연습: 암호화 애플리케이션 만들기'
description: 암호화 응용 프로그램을 만드는 과정을 안내 합니다. Windows Forms 응용 프로그램에서 콘텐츠를 암호화 하 고 암호 해독 하는 방법을 알아봅니다.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET], example
- cryptography [NET], cryptographic application example
- cryptography [NET], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 16a887f23c584daa83106ae61c497bcae8dc4dd2
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557192"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="832e6-104">연습: 암호화 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-104">Walkthrough: Creating a Cryptographic Application</span></span>

> [!NOTE]
> <span data-ttu-id="832e6-105">이 문서는 Windows에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-105">This article applies to Windows.</span></span>
>
> <span data-ttu-id="832e6-106">ASP.NET Core에 대 한 자세한 내용은 [데이터 보호 ASP.NET Core](/aspnet/core/security/data-protection/introduction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="832e6-106">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="832e6-107">이 연습에서는 콘텐츠를 암호화 및 암호 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-107">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="832e6-108">코드 예제는 Windows Forms 애플리케이션용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-108">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="832e6-109">이 애플리케이션은 스마트 카드 사용과 같은 실제 시나리오를 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-109">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="832e6-110">대신, 암호화 및 암호 해독의 기초를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-110">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
<span data-ttu-id="832e6-111">이 연습에서는 암호화에 대한 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-111">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="832e6-112">대칭 알고리즘인 <xref:System.Security.Cryptography.Aes> 클래스를 사용하여 자동으로 생성된 해당 <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> 및 <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>를 통해 데이터를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-112">Use the <xref:System.Security.Cryptography.Aes> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="832e6-113"><xref:System.Security.Cryptography.RSA>비대칭 알고리즘을 사용 하 여로 암호화 된 데이터에 대 한 키를 암호화 하 고 해독 <xref:System.Security.Cryptography.Aes> 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-113">Use the <xref:System.Security.Cryptography.RSA> asymmetric algorithm to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.Aes>.</span></span> <span data-ttu-id="832e6-114">비대칭 알고리즘은 키와 같은 적은 양의 데이터에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-114">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="832e6-115">암호화 된 콘텐츠를 다른 사용자와 교환 하지 않고 컴퓨터의 데이터를 보호 하려는 경우 클래스를 사용 하는 것이 좋습니다 <xref:System.Security.Cryptography.ProtectedData> .</span><span class="sxs-lookup"><span data-stu-id="832e6-115">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> class.</span></span>  
  
 <span data-ttu-id="832e6-116">다음 표에는 이 항목의 암호화 작업이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-116">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="832e6-117">Task</span><span class="sxs-lookup"><span data-stu-id="832e6-117">Task</span></span>|<span data-ttu-id="832e6-118">Description</span><span class="sxs-lookup"><span data-stu-id="832e6-118">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="832e6-119">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-119">Creating a Windows Forms application</span></span>|<span data-ttu-id="832e6-120">애플리케이션을 실행하는 데 필요한 컨트롤을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-120">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="832e6-121">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="832e6-121">Declaring global objects</span></span>|<span data-ttu-id="832e6-122"><xref:System.Windows.Forms.Form> 클래스의 전역 컨텍스트를 사용하도록 문자열 경로 변수, <xref:System.Security.Cryptography.CspParameters> 및 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-122">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="832e6-123">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-123">Creating an asymmetric key</span></span>|<span data-ttu-id="832e6-124">비대칭 퍼블릭 및 프라이빗 키 값 쌍을 만들고 키 컨테이너 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-124">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="832e6-125">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="832e6-125">Encrypting a file</span></span>|<span data-ttu-id="832e6-126">암호화를 위해 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-126">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="832e6-127">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="832e6-127">Decrypting a file</span></span>|<span data-ttu-id="832e6-128">암호 해독을 위해 암호화된 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-128">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="832e6-129">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-129">Getting a private key</span></span>|<span data-ttu-id="832e6-130">키 컨테이너 이름을 사용하여 전체 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-130">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="832e6-131">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="832e6-131">Exporting a public key</span></span>|<span data-ttu-id="832e6-132">public 매개 변수만 사용하여 키를 XML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-132">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="832e6-133">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-133">Importing a public key</span></span>|<span data-ttu-id="832e6-134">XML 파일의 키를 키 컨테이너에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-134">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="832e6-135">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="832e6-135">Testing the application</span></span>|<span data-ttu-id="832e6-136">이 애플리케이션을 테스트하기 위한 절차를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-136">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="832e6-137">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="832e6-137">Prerequisites</span></span>  

<span data-ttu-id="832e6-138">이 연습을 완료하려면 다음과 같은 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-138">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="832e6-139"><xref:System.IO> 및 <xref:System.Security.Cryptography> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="832e6-139">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="832e6-140">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-140">Creating a Windows Forms Application</span></span>  

<span data-ttu-id="832e6-141">이 연습의 대다수 코드 예제는 단추 컨트롤에 대한 이벤트 처리기로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-141">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="832e6-142">다음 표에서는 샘플 애플리케이션에 필요한 컨트롤 및 코드 예제와 일치하는 데 필요한 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-142">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="832e6-143">제어</span><span class="sxs-lookup"><span data-stu-id="832e6-143">Control</span></span>|<span data-ttu-id="832e6-144">이름</span><span class="sxs-lookup"><span data-stu-id="832e6-144">Name</span></span>|<span data-ttu-id="832e6-145">텍스트 속성(필요에 따라)</span><span class="sxs-lookup"><span data-stu-id="832e6-145">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="832e6-146">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="832e6-146">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="832e6-147">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="832e6-147">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="832e6-148">키 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-148">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="832e6-149">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="832e6-149">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="832e6-150">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-150">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="832e6-151">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-151">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="832e6-152">키가 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="832e6-152">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="832e6-153">Visual Studio 디자이너에서 단추를 두 번 클릭 하 여 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-153">Double-click the buttons in the Visual Studio designer to create their event handlers.</span></span>
  
## <a name="declaring-global-objects"></a><span data-ttu-id="832e6-154">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="832e6-154">Declaring Global Objects</span></span>  

<span data-ttu-id="832e6-155">폼의 생성자에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-155">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="832e6-156">사용자 환경 및 기본 설정에 맞게 문자열 변수를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-156">Edit the string variables for your environment and preferences.</span></span>  
  
[!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
[!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="832e6-157">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="832e6-157">Creating an Asymmetric Key</span></span>  

<span data-ttu-id="832e6-158">이 작업은 <xref:System.Security.Cryptography.Aes> 키를 암호화 및 암호 해독하는 비대칭 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-158">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.Aes> key.</span></span> <span data-ttu-id="832e6-159">이 키는 콘텐츠를 암호화하는 데 사용되었으며 레이블 컨트롤에 키 컨테이너 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-159">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="832e6-160">`Create Keys` 단추(`buttonCreateAsmKeys_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-160">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="832e6-161">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="832e6-161">Encrypting a File</span></span>  

<span data-ttu-id="832e6-162">이 작업에는 단추에 대 한 이벤트 처리기 메서드 `Encrypt File` ( `buttonEncryptFile_Click` ) 및 `EncryptFile` 메서드에 대 한 두 가지 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-162">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="832e6-163">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호화를 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-163">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
<span data-ttu-id="832e6-164">암호화된 콘텐츠, 키 및 IV가 모두 하나의 <xref:System.IO.FileStream>에 저장되며, 이를 암호화 패키지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-164">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
<span data-ttu-id="832e6-165">`EncryptFile` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-165">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="832e6-166"><xref:System.Security.Cryptography.Aes> 대칭 알고리즘을 만들어 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-166">Creates a <xref:System.Security.Cryptography.Aes> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="832e6-167"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.Aes> 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-167">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
3. <span data-ttu-id="832e6-168"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 소스 파일의 <xref:System.IO.FileStream>을 바이트 블록 단위로 암호화된 파일의 대상 <xref:System.IO.FileStream> 개체로 읽고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-168">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="832e6-169">암호화된 키 및 IV의 길이를 확인하고 해당 길이 값의 바이트 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-169">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="832e6-170">암호화된 패키지에 키, IV 및 해당 길이 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-170">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="832e6-171">암호화 패키지는 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-171">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="832e6-172">키 길이, 0-3바이트</span><span class="sxs-lookup"><span data-stu-id="832e6-172">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="832e6-173">IV 길이, 4-7바이트</span><span class="sxs-lookup"><span data-stu-id="832e6-173">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="832e6-174">암호화된 키</span><span class="sxs-lookup"><span data-stu-id="832e6-174">Encrypted key</span></span>  
  
- <span data-ttu-id="832e6-175">IV</span><span class="sxs-lookup"><span data-stu-id="832e6-175">IV</span></span>  
  
- <span data-ttu-id="832e6-176">암호화 텍스트</span><span class="sxs-lookup"><span data-stu-id="832e6-176">Cipher text</span></span>  
  
 <span data-ttu-id="832e6-177">키 및 IV의 길이를 사용하여 파일을 암호 해독하는 데 사용할 수 있는 암호화 패키지의 모든 부분에 대한 시작 지점 및 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-177">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="832e6-178">`Encrypt File` 단추(`buttonEncryptFile_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-178">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="832e6-179">다음 `EncryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-179">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="832e6-180">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="832e6-180">Decrypting a File</span></span>  

<span data-ttu-id="832e6-181">이 작업에는 `Decrypt File` 단추에 대한 이벤트 처리기 메서드(`buttonDecryptFile_Click`) 및 `DecryptFile` 메서드의 두 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-181">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="832e6-182">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호 해독을 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-182">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
<span data-ttu-id="832e6-183">`Decrypt` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-183">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="832e6-184">콘텐츠를 <xref:System.Security.Cryptography.Aes> 해독 하는 대칭 알고리즘을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-184">Creates an <xref:System.Security.Cryptography.Aes> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="832e6-185">암호화된 패키지 <xref:System.IO.FileStream>의 처음 8바이트를 바이트 배열로 읽어 암호화된 키 및 IV의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-185">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="832e6-186">암호화 패키지에서 바이트 배열로 키 및 IV를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-186">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="832e6-187"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.Aes> 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-187">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.Aes> key.</span></span>  
  
5. <span data-ttu-id="832e6-188"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 <xref:System.IO.FileStream> 암호화 패키지의 암호화 텍스트 섹션을 바이트 블록 단위로 암호 해독된 파일의 <xref:System.IO.FileStream> 개체로 읽고 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-188">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="832e6-189">이 작업을 완료하면 암호 해독이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-189">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="832e6-190">`Decrypt File` 단추에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-190">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="832e6-191">다음 `DecryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-191">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="832e6-192">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="832e6-192">Exporting a Public Key</span></span>

<span data-ttu-id="832e6-193">이 작업은 `Create Keys` 단추를 사용하여 만든 키를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-193">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="832e6-194">public 매개 변수만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-194">It exports only the public parameters.</span></span>  
  
<span data-ttu-id="832e6-195">이 작업은 Bob이 파일을 암호화할 수 있도록 Alice가 Bob에게 공개 키를 제공하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-195">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="832e6-196">Bob과 해당 공개 키를 가진 다른 사용자는 private 매개 변수가 있는 전체 키 쌍이 없기 때문에 파일을 암호 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-196">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="832e6-197">`Export Public Key` 단추(`buttonExportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-197">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
[!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="832e6-198">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-198">Importing a Public Key</span></span>

<span data-ttu-id="832e6-199">이 작업은 `Export Public Key` 단추를 사용하여 만든 public 매개 변수만 있는 키를 로드하고 키 컨테이너 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-199">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
<span data-ttu-id="832e6-200">이 작업은 Bob이 파일을 암호화할 수 있도록 public 매개 변수만 있는 Alice의 키를 Bob이 로드하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-200">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
<span data-ttu-id="832e6-201">`Import Public Key` 단추(`buttonImportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-201">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
[!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="832e6-202">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="832e6-202">Getting a Private Key</span></span>  

<span data-ttu-id="832e6-203">이 작업은 키 컨테이너 이름을 `Create Keys` 단추를 사용하여 만든 키의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-203">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="832e6-204">키 컨테이너는 private 매개 변수가 있는 전체 키 쌍을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-204">The key container will contain the full key pair with private parameters.</span></span>  
  
<span data-ttu-id="832e6-205">이 작업은 Alice가 프라이빗 키를 사용하여 Bob이 암호화한 파일을 암호 해독하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-205">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
<span data-ttu-id="832e6-206">`Get Private Key` 단추(`buttonGetPrivateKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-206">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
[!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
[!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="832e6-207">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="832e6-207">Testing the Application</span></span>

<span data-ttu-id="832e6-208">애플리케이션을 빌드한 후 다음과 같은 테스트 시나리오를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-208">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="832e6-209">키를 만들고 암호화 및 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="832e6-209">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="832e6-210">`Create Keys` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-210">Click the `Create Keys` button.</span></span> <span data-ttu-id="832e6-211">레이블이 키 이름을 표시하고 전체 키 쌍임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-211">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="832e6-212">`Export Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-212">Click the `Export Public Key` button.</span></span> <span data-ttu-id="832e6-213">공개 키 매개 변수를 내보내는 경우 현재 키가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-213">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="832e6-214">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-214">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="832e6-215">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-215">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="832e6-216">방금 암호 해독한 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-216">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="832e6-217">애플리케이션을 닫고 다음 시나리오에서 지속형 키 컨테이너 검색을 테스트하기 위해 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-217">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="832e6-218">공개 키를 사용하여 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="832e6-218">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="832e6-219">`Import Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-219">Click the `Import Public Key` button.</span></span> <span data-ttu-id="832e6-220">레이블이 키 이름을 표시하고 public 전용임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-220">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="832e6-221">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-221">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="832e6-222">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-222">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="832e6-223">암호 해독하려면 프라이빗 키가 있어야 하므로 이 작업은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-223">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="832e6-224">이 시나리오에서는 다른 사용자를 위해 파일을 암호화할 공개 키만 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-224">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="832e6-225">일반적으로 해당 사용자는 퍼블릭 키만 제공하고 암호 해독을 위한 프라이빗 키는 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-225">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="832e6-226">프라이빗 키를 사용하여 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="832e6-226">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="832e6-227">`Get Private Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-227">Click the `Get Private Key` button.</span></span> <span data-ttu-id="832e6-228">레이블이 키 이름을 표시하고 전체 키 쌍인지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-228">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="832e6-229">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-229">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="832e6-230">암호 해독을 위한 전체 키 쌍이 있으므로 이 작업은 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-230">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832e6-231">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832e6-231">See also</span></span>

- <span data-ttu-id="832e6-232">[암호화 모델](cryptography-model.md) -기본 클래스 라이브러리에서 암호화가 구현 되는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e6-232">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="832e6-233">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="832e6-233">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="832e6-234">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="832e6-234">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="832e6-235">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="832e6-235">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
