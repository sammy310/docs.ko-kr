---
title: '연습: 암호화 응용 프로그램 만들기'
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
ms.openlocfilehash: 6e2d9b8bebdfd2ea5d5507cc73d444fa8bf785fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705836"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="fed5f-102">연습: 암호화 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="fed5f-103">이 연습에서는 콘텐츠를 암호화 및 암호 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="fed5f-104">코드 예제는 Windows Forms 애플리케이션용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="fed5f-105">이 애플리케이션은 스마트 카드 사용과 같은 실제 시나리오를 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="fed5f-106">대신, 암호화 및 암호 해독의 기초를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="fed5f-107">이 연습에서는 암호화에 대한 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="fed5f-108">대칭 알고리즘인 <xref:System.Security.Cryptography.RijndaelManaged> 클래스를 사용하여 자동으로 생성된 해당 <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> 및 <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>를 통해 데이터를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="fed5f-109">비대칭 알고리즘인 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 사용하여 <xref:System.Security.Cryptography.RijndaelManaged>를 통해 암호화된 데이터에 대한 키를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="fed5f-110">비대칭 알고리즘은 키와 같은 적은 양의 데이터에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fed5f-111">암호화된 콘텐츠를 다른 사용자와 교환하는 대신 컴퓨터에서 데이터를 보호하려는 경우 <xref:System.Security.Cryptography.ProtectedData> 또는 <xref:System.Security.Cryptography.ProtectedMemory> 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="fed5f-112">다음 표에는 이 항목의 암호화 작업이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="fed5f-113">작업</span><span class="sxs-lookup"><span data-stu-id="fed5f-113">Task</span></span>|<span data-ttu-id="fed5f-114">설명</span><span class="sxs-lookup"><span data-stu-id="fed5f-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="fed5f-115">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="fed5f-116">애플리케이션을 실행하는 데 필요한 컨트롤을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="fed5f-117">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="fed5f-117">Declaring global objects</span></span>|<span data-ttu-id="fed5f-118"><xref:System.Windows.Forms.Form> 클래스의 전역 컨텍스트를 사용하도록 문자열 경로 변수, <xref:System.Security.Cryptography.CspParameters> 및 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="fed5f-119">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-119">Creating an asymmetric key</span></span>|<span data-ttu-id="fed5f-120">비대칭 퍼블릭 및 프라이빗 키 값 쌍을 만들고 키 컨테이너 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="fed5f-121">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="fed5f-121">Encrypting a file</span></span>|<span data-ttu-id="fed5f-122">암호화를 위해 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="fed5f-123">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="fed5f-123">Decrypting a file</span></span>|<span data-ttu-id="fed5f-124">암호 해독을 위해 암호화된 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="fed5f-125">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-125">Getting a private key</span></span>|<span data-ttu-id="fed5f-126">키 컨테이너 이름을 사용하여 전체 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="fed5f-127">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="fed5f-127">Exporting a public key</span></span>|<span data-ttu-id="fed5f-128">public 매개 변수만 사용하여 키를 XML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="fed5f-129">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-129">Importing a public key</span></span>|<span data-ttu-id="fed5f-130">XML 파일의 키를 키 컨테이너에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="fed5f-131">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="fed5f-131">Testing the application</span></span>|<span data-ttu-id="fed5f-132">이 애플리케이션을 테스트하기 위한 절차를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="fed5f-133">전제 조건</span><span class="sxs-lookup"><span data-stu-id="fed5f-133">Prerequisites</span></span>  
 <span data-ttu-id="fed5f-134">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-134">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="fed5f-135"><xref:System.IO> 및 <xref:System.Security.Cryptography> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fed5f-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="fed5f-136">Windows Forms 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="fed5f-137">이 연습의 대다수 코드 예제는 단추 컨트롤에 대한 이벤트 처리기로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="fed5f-138">다음 표에서는 샘플 애플리케이션에 필요한 컨트롤 및 코드 예제와 일치하는 데 필요한 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="fed5f-139">Control</span><span class="sxs-lookup"><span data-stu-id="fed5f-139">Control</span></span>|<span data-ttu-id="fed5f-140">이름</span><span class="sxs-lookup"><span data-stu-id="fed5f-140">Name</span></span>|<span data-ttu-id="fed5f-141">텍스트 속성(필요에 따라)</span><span class="sxs-lookup"><span data-stu-id="fed5f-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="fed5f-142">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="fed5f-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="fed5f-143">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="fed5f-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="fed5f-144">키 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="fed5f-145">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="fed5f-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="fed5f-146">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="fed5f-147">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="fed5f-148">키가 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="fed5f-148">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="fed5f-149">이벤트 처리기를 만들려면 Visual Studio 디자이너에서 해당 단추를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-149">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="fed5f-150">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="fed5f-150">Declaring Global Objects</span></span>  
 <span data-ttu-id="fed5f-151">폼의 생성자에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-151">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="fed5f-152">사용자 환경 및 기본 설정에 맞게 문자열 변수를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-152">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="fed5f-153">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="fed5f-153">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="fed5f-154">이 작업은 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화 및 암호 해독하는 비대칭 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-154">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="fed5f-155">이 키는 콘텐츠를 암호화하는 데 사용되었으며 레이블 컨트롤에 키 컨테이너 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-155">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="fed5f-156">`Create Keys` 단추(`buttonCreateAsmKeys_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-156">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="fed5f-157">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="fed5f-157">Encrypting a File</span></span>  
 <span data-ttu-id="fed5f-158">이 작업에는 `Encrypt File` 단추에 대 한 이벤트 처리기 메서드 (`buttonEncryptFile_Click`) 및 `EncryptFile` 메서드에 대 한 두 가지 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-158">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="fed5f-159">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호화를 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-159">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="fed5f-160">암호화된 콘텐츠, 키 및 IV가 모두 하나의 <xref:System.IO.FileStream>에 저장되며, 이를 암호화 패키지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-160">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="fed5f-161">`EncryptFile` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-161">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="fed5f-162"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-162">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="fed5f-163"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-163">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="fed5f-164"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 소스 파일의 <xref:System.IO.FileStream>을 바이트 블록 단위로 암호화된 파일의 대상 <xref:System.IO.FileStream> 개체로 읽고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-164">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="fed5f-165">암호화된 키 및 IV의 길이를 확인하고 해당 길이 값의 바이트 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-165">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="fed5f-166">암호화된 패키지에 키, IV 및 해당 길이 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-166">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="fed5f-167">암호화 패키지는 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-167">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="fed5f-168">키 길이, 0-3바이트</span><span class="sxs-lookup"><span data-stu-id="fed5f-168">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="fed5f-169">IV 길이, 4-7바이트</span><span class="sxs-lookup"><span data-stu-id="fed5f-169">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="fed5f-170">암호화된 키</span><span class="sxs-lookup"><span data-stu-id="fed5f-170">Encrypted key</span></span>  
  
- <span data-ttu-id="fed5f-171">IV</span><span class="sxs-lookup"><span data-stu-id="fed5f-171">IV</span></span>  
  
- <span data-ttu-id="fed5f-172">암호화 텍스트</span><span class="sxs-lookup"><span data-stu-id="fed5f-172">Cipher text</span></span>  
  
 <span data-ttu-id="fed5f-173">키 및 IV의 길이를 사용하여 파일을 암호 해독하는 데 사용할 수 있는 암호화 패키지의 모든 부분에 대한 시작 지점 및 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-173">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="fed5f-174">`Encrypt File` 단추(`buttonEncryptFile_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-174">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="fed5f-175">다음 `EncryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-175">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="fed5f-176">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="fed5f-176">Decrypting a File</span></span>  
 <span data-ttu-id="fed5f-177">이 작업에는 `Decrypt File` 단추에 대한 이벤트 처리기 메서드(`buttonDecryptFile_Click`) 및 `DecryptFile` 메서드의 두 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-177">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="fed5f-178">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호 해독을 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-178">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="fed5f-179">`Decrypt` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-179">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="fed5f-180"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-180">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="fed5f-181">암호화된 패키지 <xref:System.IO.FileStream>의 처음 8바이트를 바이트 배열로 읽어 암호화된 키 및 IV의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-181">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="fed5f-182">암호화 패키지에서 바이트 배열로 키 및 IV를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-182">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="fed5f-183"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-183">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="fed5f-184"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 <xref:System.IO.FileStream> 암호화 패키지의 암호화 텍스트 섹션을 바이트 블록 단위로 암호 해독된 파일의 <xref:System.IO.FileStream> 개체로 읽고 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-184">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="fed5f-185">이 작업을 완료하면 암호 해독이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-185">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="fed5f-186">`Decrypt File` 단추에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-186">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="fed5f-187">다음 `DecryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-187">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="fed5f-188">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="fed5f-188">Exporting a Public Key</span></span>  
 <span data-ttu-id="fed5f-189">이 작업은 `Create Keys` 단추를 사용하여 만든 키를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-189">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="fed5f-190">public 매개 변수만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-190">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="fed5f-191">이 작업은 Bob이 파일을 암호화할 수 있도록 Alice가 Bob에게 공개 키를 제공하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-191">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="fed5f-192">Bob과 해당 공개 키를 가진 다른 사용자는 private 매개 변수가 있는 전체 키 쌍이 없기 때문에 파일을 암호 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-192">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="fed5f-193">`Export Public Key` 단추(`buttonExportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-193">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="fed5f-194">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-194">Importing a Public Key</span></span>  
 <span data-ttu-id="fed5f-195">이 작업은 `Export Public Key` 단추를 사용하여 만든 public 매개 변수만 있는 키를 로드하고 키 컨테이너 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-195">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="fed5f-196">이 작업은 Bob이 파일을 암호화할 수 있도록 public 매개 변수만 있는 Alice의 키를 Bob이 로드하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-196">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="fed5f-197">`Import Public Key` 단추(`buttonImportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-197">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="fed5f-198">프라이빗 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="fed5f-198">Getting a Private Key</span></span>  
 <span data-ttu-id="fed5f-199">이 작업은 키 컨테이너 이름을 `Create Keys` 단추를 사용하여 만든 키의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-199">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="fed5f-200">키 컨테이너는 private 매개 변수가 있는 전체 키 쌍을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-200">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="fed5f-201">이 작업은 Alice가 프라이빗 키를 사용하여 Bob이 암호화한 파일을 암호 해독하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-201">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="fed5f-202">`Get Private Key` 단추(`buttonGetPrivateKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-202">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="fed5f-203">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="fed5f-203">Testing the Application</span></span>  
 <span data-ttu-id="fed5f-204">애플리케이션을 빌드한 후 다음과 같은 테스트 시나리오를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-204">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="fed5f-205">키를 만들고 암호화 및 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="fed5f-205">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="fed5f-206">`Create Keys` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-206">Click the `Create Keys` button.</span></span> <span data-ttu-id="fed5f-207">레이블이 키 이름을 표시하고 전체 키 쌍임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-207">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="fed5f-208">`Export Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-208">Click the `Export Public Key` button.</span></span> <span data-ttu-id="fed5f-209">공개 키 매개 변수를 내보내는 경우 현재 키가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-209">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="fed5f-210">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-210">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="fed5f-211">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-211">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="fed5f-212">방금 암호 해독한 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-212">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="fed5f-213">애플리케이션을 닫고 다음 시나리오에서 지속형 키 컨테이너 검색을 테스트하기 위해 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-213">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="fed5f-214">공개 키를 사용하여 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="fed5f-214">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="fed5f-215">`Import Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-215">Click the `Import Public Key` button.</span></span> <span data-ttu-id="fed5f-216">레이블이 키 이름을 표시하고 public 전용임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-216">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="fed5f-217">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-217">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="fed5f-218">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-218">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="fed5f-219">암호 해독하려면 프라이빗 키가 있어야 하므로 이 작업은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-219">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="fed5f-220">이 시나리오에서는 다른 사용자를 위해 파일을 암호화할 공개 키만 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-220">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="fed5f-221">일반적으로 해당 사용자는 퍼블릭 키만 제공하고 암호 해독을 위한 프라이빗 키는 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-221">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="fed5f-222">프라이빗 키를 사용하여 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="fed5f-222">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="fed5f-223">`Get Private Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-223">Click the `Get Private Key` button.</span></span> <span data-ttu-id="fed5f-224">레이블이 키 이름을 표시하고 전체 키 쌍인지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-224">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="fed5f-225">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-225">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="fed5f-226">암호 해독을 위한 전체 키 쌍이 있으므로 이 작업은 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="fed5f-226">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed5f-227">참조</span><span class="sxs-lookup"><span data-stu-id="fed5f-227">See also</span></span>

- [<span data-ttu-id="fed5f-228">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="fed5f-228">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
