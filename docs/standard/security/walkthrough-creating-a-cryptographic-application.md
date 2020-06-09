---
title: '연습: 암호화 애플리케이션 만들기'
description: 암호화 응용 프로그램을 만드는 과정을 안내 합니다. Windows Forms 응용 프로그램에서 콘텐츠를 암호화 하 고 암호 해독 하는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 72116227fbec2435d428ad2bbdb4cc74e5c3663f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602182"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="9280b-104">연습: 암호화 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-104">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="9280b-105">이 연습에서는 콘텐츠를 암호화 및 암호 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-105">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="9280b-106">코드 예제는 Windows Forms 애플리케이션용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-106">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="9280b-107">이 애플리케이션은 스마트 카드 사용과 같은 실제 시나리오를 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-107">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="9280b-108">대신, 암호화 및 암호 해독의 기초를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-108">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="9280b-109">이 연습에서는 암호화에 대한 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-109">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="9280b-110">대칭 알고리즘인 <xref:System.Security.Cryptography.RijndaelManaged> 클래스를 사용하여 자동으로 생성된 해당 <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> 및 <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>를 통해 데이터를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-110">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="9280b-111">비대칭 알고리즘인 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 사용하여 <xref:System.Security.Cryptography.RijndaelManaged>를 통해 암호화된 데이터에 대한 키를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-111">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="9280b-112">비대칭 알고리즘은 키와 같은 적은 양의 데이터에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-112">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9280b-113">암호화된 콘텐츠를 다른 사용자와 교환하는 대신 컴퓨터에서 데이터를 보호하려는 경우 <xref:System.Security.Cryptography.ProtectedData> 또는 <xref:System.Security.Cryptography.ProtectedMemory> 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-113">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="9280b-114">다음 표에는 이 항목의 암호화 작업이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-114">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="9280b-115">Task</span><span class="sxs-lookup"><span data-stu-id="9280b-115">Task</span></span>|<span data-ttu-id="9280b-116">Description</span><span class="sxs-lookup"><span data-stu-id="9280b-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9280b-117">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-117">Creating a Windows Forms application</span></span>|<span data-ttu-id="9280b-118">애플리케이션을 실행하는 데 필요한 컨트롤을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-118">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="9280b-119">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="9280b-119">Declaring global objects</span></span>|<span data-ttu-id="9280b-120"><xref:System.Windows.Forms.Form> 클래스의 전역 컨텍스트를 사용하도록 문자열 경로 변수, <xref:System.Security.Cryptography.CspParameters> 및 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-120">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="9280b-121">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-121">Creating an asymmetric key</span></span>|<span data-ttu-id="9280b-122">비대칭 퍼블릭 및 프라이빗 키 값 쌍을 만들고 키 컨테이너 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-122">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="9280b-123">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="9280b-123">Encrypting a file</span></span>|<span data-ttu-id="9280b-124">암호화를 위해 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-124">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="9280b-125">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="9280b-125">Decrypting a file</span></span>|<span data-ttu-id="9280b-126">암호 해독을 위해 암호화된 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-126">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="9280b-127">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-127">Getting a private key</span></span>|<span data-ttu-id="9280b-128">키 컨테이너 이름을 사용하여 전체 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-128">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="9280b-129">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="9280b-129">Exporting a public key</span></span>|<span data-ttu-id="9280b-130">public 매개 변수만 사용하여 키를 XML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-130">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="9280b-131">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-131">Importing a public key</span></span>|<span data-ttu-id="9280b-132">XML 파일의 키를 키 컨테이너에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-132">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="9280b-133">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="9280b-133">Testing the application</span></span>|<span data-ttu-id="9280b-134">이 애플리케이션을 테스트하기 위한 절차를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-134">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="9280b-135">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9280b-135">Prerequisites</span></span>  
 <span data-ttu-id="9280b-136">이 연습을 완료하려면 다음과 같은 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-136">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="9280b-137"><xref:System.IO> 및 <xref:System.Security.Cryptography> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="9280b-137">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="9280b-138">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-138">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="9280b-139">이 연습의 대다수 코드 예제는 단추 컨트롤에 대한 이벤트 처리기로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-139">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="9280b-140">다음 표에서는 샘플 애플리케이션에 필요한 컨트롤 및 코드 예제와 일치하는 데 필요한 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-140">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="9280b-141">제어</span><span class="sxs-lookup"><span data-stu-id="9280b-141">Control</span></span>|<span data-ttu-id="9280b-142">Name</span><span class="sxs-lookup"><span data-stu-id="9280b-142">Name</span></span>|<span data-ttu-id="9280b-143">텍스트 속성(필요에 따라)</span><span class="sxs-lookup"><span data-stu-id="9280b-143">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="9280b-144">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="9280b-144">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="9280b-145">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="9280b-145">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="9280b-146">키 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-146">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="9280b-147">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="9280b-147">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="9280b-148">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-148">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="9280b-149">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-149">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="9280b-150">키가 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9280b-150">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="9280b-151">이벤트 처리기를 만들려면 Visual Studio 디자이너에서 해당 단추를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-151">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="9280b-152">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="9280b-152">Declaring Global Objects</span></span>  
 <span data-ttu-id="9280b-153">폼의 생성자에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-153">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="9280b-154">사용자 환경 및 기본 설정에 맞게 문자열 변수를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-154">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="9280b-155">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="9280b-155">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="9280b-156">이 작업은 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화 및 암호 해독하는 비대칭 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-156">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="9280b-157">이 키는 콘텐츠를 암호화하는 데 사용되었으며 레이블 컨트롤에 키 컨테이너 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-157">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="9280b-158">`Create Keys` 단추(`buttonCreateAsmKeys_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-158">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="9280b-159">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="9280b-159">Encrypting a File</span></span>  
 <span data-ttu-id="9280b-160">이 작업에는 단추에 대 한 이벤트 처리기 메서드 `Encrypt File` ( `buttonEncryptFile_Click` ) 및 `EncryptFile` 메서드에 대 한 두 가지 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-160">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="9280b-161">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호화를 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-161">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="9280b-162">암호화된 콘텐츠, 키 및 IV가 모두 하나의 <xref:System.IO.FileStream>에 저장되며, 이를 암호화 패키지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-162">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="9280b-163">`EncryptFile` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-163">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="9280b-164"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-164">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="9280b-165"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-165">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="9280b-166"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 소스 파일의 <xref:System.IO.FileStream>을 바이트 블록 단위로 암호화된 파일의 대상 <xref:System.IO.FileStream> 개체로 읽고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-166">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="9280b-167">암호화된 키 및 IV의 길이를 확인하고 해당 길이 값의 바이트 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-167">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="9280b-168">암호화된 패키지에 키, IV 및 해당 길이 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-168">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="9280b-169">암호화 패키지는 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-169">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="9280b-170">키 길이, 0-3바이트</span><span class="sxs-lookup"><span data-stu-id="9280b-170">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="9280b-171">IV 길이, 4-7바이트</span><span class="sxs-lookup"><span data-stu-id="9280b-171">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="9280b-172">암호화된 키</span><span class="sxs-lookup"><span data-stu-id="9280b-172">Encrypted key</span></span>  
  
- <span data-ttu-id="9280b-173">IV</span><span class="sxs-lookup"><span data-stu-id="9280b-173">IV</span></span>  
  
- <span data-ttu-id="9280b-174">암호화 텍스트</span><span class="sxs-lookup"><span data-stu-id="9280b-174">Cipher text</span></span>  
  
 <span data-ttu-id="9280b-175">키 및 IV의 길이를 사용하여 파일을 암호 해독하는 데 사용할 수 있는 암호화 패키지의 모든 부분에 대한 시작 지점 및 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-175">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="9280b-176">`Encrypt File` 단추(`buttonEncryptFile_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-176">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="9280b-177">다음 `EncryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-177">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="9280b-178">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="9280b-178">Decrypting a File</span></span>  
 <span data-ttu-id="9280b-179">이 작업에는 `Decrypt File` 단추에 대한 이벤트 처리기 메서드(`buttonDecryptFile_Click`) 및 `DecryptFile` 메서드의 두 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-179">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="9280b-180">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호 해독을 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-180">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="9280b-181">`Decrypt` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-181">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="9280b-182"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-182">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="9280b-183">암호화된 패키지 <xref:System.IO.FileStream>의 처음 8바이트를 바이트 배열로 읽어 암호화된 키 및 IV의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-183">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="9280b-184">암호화 패키지에서 바이트 배열로 키 및 IV를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-184">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="9280b-185"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-185">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="9280b-186"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 <xref:System.IO.FileStream> 암호화 패키지의 암호화 텍스트 섹션을 바이트 블록 단위로 암호 해독된 파일의 <xref:System.IO.FileStream> 개체로 읽고 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-186">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="9280b-187">이 작업을 완료하면 암호 해독이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-187">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="9280b-188">`Decrypt File` 단추에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-188">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="9280b-189">다음 `DecryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-189">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="9280b-190">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="9280b-190">Exporting a Public Key</span></span>  
 <span data-ttu-id="9280b-191">이 작업은 `Create Keys` 단추를 사용하여 만든 키를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-191">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="9280b-192">public 매개 변수만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-192">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="9280b-193">이 작업은 Bob이 파일을 암호화할 수 있도록 Alice가 Bob에게 공개 키를 제공하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-193">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="9280b-194">Bob과 해당 공개 키를 가진 다른 사용자는 private 매개 변수가 있는 전체 키 쌍이 없기 때문에 파일을 암호 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-194">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="9280b-195">`Export Public Key` 단추(`buttonExportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-195">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="9280b-196">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-196">Importing a Public Key</span></span>  
 <span data-ttu-id="9280b-197">이 작업은 `Export Public Key` 단추를 사용하여 만든 public 매개 변수만 있는 키를 로드하고 키 컨테이너 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-197">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="9280b-198">이 작업은 Bob이 파일을 암호화할 수 있도록 public 매개 변수만 있는 Alice의 키를 Bob이 로드하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-198">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="9280b-199">`Import Public Key` 단추(`buttonImportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-199">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="9280b-200">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="9280b-200">Getting a Private Key</span></span>  
 <span data-ttu-id="9280b-201">이 작업은 키 컨테이너 이름을 `Create Keys` 단추를 사용하여 만든 키의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-201">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="9280b-202">키 컨테이너는 private 매개 변수가 있는 전체 키 쌍을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-202">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="9280b-203">이 작업은 Alice가 프라이빗 키를 사용하여 Bob이 암호화한 파일을 암호 해독하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-203">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="9280b-204">`Get Private Key` 단추(`buttonGetPrivateKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-204">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="9280b-205">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="9280b-205">Testing the Application</span></span>  
 <span data-ttu-id="9280b-206">애플리케이션을 빌드한 후 다음과 같은 테스트 시나리오를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-206">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="9280b-207">키를 만들고 암호화 및 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="9280b-207">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="9280b-208">`Create Keys` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-208">Click the `Create Keys` button.</span></span> <span data-ttu-id="9280b-209">레이블이 키 이름을 표시하고 전체 키 쌍임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-209">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="9280b-210">`Export Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-210">Click the `Export Public Key` button.</span></span> <span data-ttu-id="9280b-211">공개 키 매개 변수를 내보내는 경우 현재 키가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-211">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="9280b-212">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-212">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="9280b-213">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-213">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="9280b-214">방금 암호 해독한 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-214">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="9280b-215">애플리케이션을 닫고 다음 시나리오에서 지속형 키 컨테이너 검색을 테스트하기 위해 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-215">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="9280b-216">공개 키를 사용하여 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="9280b-216">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="9280b-217">`Import Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-217">Click the `Import Public Key` button.</span></span> <span data-ttu-id="9280b-218">레이블이 키 이름을 표시하고 public 전용임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-218">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="9280b-219">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-219">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="9280b-220">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-220">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="9280b-221">암호 해독하려면 프라이빗 키가 있어야 하므로 이 작업은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-221">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="9280b-222">이 시나리오에서는 다른 사용자를 위해 파일을 암호화할 공개 키만 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-222">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="9280b-223">일반적으로 해당 사용자는 퍼블릭 키만 제공하고 암호 해독을 위한 프라이빗 키는 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-223">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="9280b-224">프라이빗 키를 사용하여 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="9280b-224">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="9280b-225">`Get Private Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-225">Click the `Get Private Key` button.</span></span> <span data-ttu-id="9280b-226">레이블이 키 이름을 표시하고 전체 키 쌍인지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-226">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="9280b-227">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-227">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="9280b-228">암호 해독을 위한 전체 키 쌍이 있으므로 이 작업은 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="9280b-228">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9280b-229">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9280b-229">See also</span></span>

- [<span data-ttu-id="9280b-230">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="9280b-230">Cryptographic Services</span></span>](cryptographic-services.md)
