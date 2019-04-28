---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771997"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="82562-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="82562-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="82562-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82562-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="82562-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="82562-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="82562-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="82562-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="82562-106">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-106">Tables</span></span>  
  
- <span data-ttu-id="82562-107">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-107">Columns</span></span>  
  
- <span data-ttu-id="82562-108">절차</span><span class="sxs-lookup"><span data-stu-id="82562-108">Procedures</span></span>  
  
- <span data-ttu-id="82562-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="82562-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="82562-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="82562-110">Catalog</span></span>  
  
- <span data-ttu-id="82562-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="82562-112">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-112">Tables</span></span>  
  
|<span data-ttu-id="82562-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-113">ColumnName</span></span>|<span data-ttu-id="82562-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-115">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-116">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-116">String</span></span>|  
|<span data-ttu-id="82562-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-118">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-118">String</span></span>|  
|<span data-ttu-id="82562-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-119">TABLE_NAME</span></span>|<span data-ttu-id="82562-120">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-120">String</span></span>|  
|<span data-ttu-id="82562-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-121">TABLE_TYPE</span></span>|<span data-ttu-id="82562-122">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-122">String</span></span>|  
|<span data-ttu-id="82562-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-123">TABLE_GUID</span></span>|<span data-ttu-id="82562-124">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-124">Guid</span></span>|  
|<span data-ttu-id="82562-125">설명</span><span class="sxs-lookup"><span data-stu-id="82562-125">DESCRIPTION</span></span>|<span data-ttu-id="82562-126">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-126">String</span></span>|  
|<span data-ttu-id="82562-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-127">TABLE_PROPID</span></span>|<span data-ttu-id="82562-128">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-128">Int64</span></span>|  
|<span data-ttu-id="82562-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-129">DATE_CREATED</span></span>|<span data-ttu-id="82562-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-130">DateTime</span></span>|  
|<span data-ttu-id="82562-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-131">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="82562-133">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-133">Columns</span></span>  
  
|<span data-ttu-id="82562-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-134">ColumnName</span></span>|<span data-ttu-id="82562-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-136">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-137">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-137">String</span></span>|  
|<span data-ttu-id="82562-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-139">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-139">String</span></span>|  
|<span data-ttu-id="82562-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-140">TABLE_NAME</span></span>|<span data-ttu-id="82562-141">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-141">String</span></span>|  
|<span data-ttu-id="82562-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-142">COLUMN_NAME</span></span>|<span data-ttu-id="82562-143">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-143">String</span></span>|  
|<span data-ttu-id="82562-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-144">COLUMN_GUID</span></span>|<span data-ttu-id="82562-145">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-145">Guid</span></span>|  
|<span data-ttu-id="82562-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-146">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-147">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-147">Int64</span></span>|  
|<span data-ttu-id="82562-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-149">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-149">Int64</span></span>|  
|<span data-ttu-id="82562-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="82562-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-151">Boolean</span></span>|  
|<span data-ttu-id="82562-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="82562-153">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-153">String</span></span>|  
|<span data-ttu-id="82562-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="82562-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="82562-155">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-155">Int64</span></span>|  
|<span data-ttu-id="82562-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="82562-156">IS_NULLABLE</span></span>|<span data-ttu-id="82562-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-157">Boolean</span></span>|  
|<span data-ttu-id="82562-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-158">DATA_TYPE</span></span>|<span data-ttu-id="82562-159">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-159">Int32</span></span>|  
|<span data-ttu-id="82562-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-160">TYPE_GUID</span></span>|<span data-ttu-id="82562-161">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-161">Guid</span></span>|  
|<span data-ttu-id="82562-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="82562-163">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-163">Int64</span></span>|  
|<span data-ttu-id="82562-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="82562-165">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-165">Int64</span></span>|  
|<span data-ttu-id="82562-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="82562-167">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-167">Int32</span></span>|  
|<span data-ttu-id="82562-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="82562-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="82562-169">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-169">Int16</span></span>|  
|<span data-ttu-id="82562-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="82562-171">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-171">Int64</span></span>|  
|<span data-ttu-id="82562-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="82562-173">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-173">String</span></span>|  
|<span data-ttu-id="82562-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="82562-175">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-175">String</span></span>|  
|<span data-ttu-id="82562-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="82562-177">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-177">String</span></span>|  
|<span data-ttu-id="82562-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="82562-179">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-179">String</span></span>|  
|<span data-ttu-id="82562-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="82562-181">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-181">String</span></span>|  
|<span data-ttu-id="82562-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-182">COLLATION_NAME</span></span>|<span data-ttu-id="82562-183">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-183">String</span></span>|  
|<span data-ttu-id="82562-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="82562-185">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-185">String</span></span>|  
|<span data-ttu-id="82562-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="82562-187">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-187">String</span></span>|  
|<span data-ttu-id="82562-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-188">DOMAIN_NAME</span></span>|<span data-ttu-id="82562-189">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-189">String</span></span>|  
|<span data-ttu-id="82562-190">설명</span><span class="sxs-lookup"><span data-stu-id="82562-190">DESCRIPTION</span></span>|<span data-ttu-id="82562-191">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-191">String</span></span>|  
|<span data-ttu-id="82562-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="82562-192">COLUMN_LCID</span></span>|<span data-ttu-id="82562-193">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-193">Int32</span></span>|  
|<span data-ttu-id="82562-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="82562-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="82562-195">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-195">Int32</span></span>|  
|<span data-ttu-id="82562-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="82562-196">COLUMN_SORTID</span></span>|<span data-ttu-id="82562-197">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-197">Int32</span></span>|  
|<span data-ttu-id="82562-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="82562-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="82562-199">Byte[]</span></span>|  
|<span data-ttu-id="82562-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="82562-200">IS_COMPUTED</span></span>|<span data-ttu-id="82562-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="82562-202">절차</span><span class="sxs-lookup"><span data-stu-id="82562-202">Procedures</span></span>  
  
|<span data-ttu-id="82562-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-203">ColumnName</span></span>|<span data-ttu-id="82562-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="82562-206">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-206">String</span></span>|  
|<span data-ttu-id="82562-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="82562-208">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-208">String</span></span>|  
|<span data-ttu-id="82562-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="82562-210">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-210">String</span></span>|  
|<span data-ttu-id="82562-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="82562-212">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-212">Int16</span></span>|  
|<span data-ttu-id="82562-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="82562-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="82562-214">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-214">String</span></span>|  
|<span data-ttu-id="82562-215">설명</span><span class="sxs-lookup"><span data-stu-id="82562-215">DESCRIPTION</span></span>|<span data-ttu-id="82562-216">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-216">String</span></span>|  
|<span data-ttu-id="82562-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-217">DATE_CREATED</span></span>|<span data-ttu-id="82562-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-218">DateTime</span></span>|  
|<span data-ttu-id="82562-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-219">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="82562-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="82562-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="82562-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-222">ColumnName</span></span>|<span data-ttu-id="82562-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="82562-225">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-225">String</span></span>|  
|<span data-ttu-id="82562-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="82562-227">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-227">String</span></span>|  
|<span data-ttu-id="82562-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="82562-229">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-229">String</span></span>|  
|<span data-ttu-id="82562-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-230">PARAMETER_NAME</span></span>|<span data-ttu-id="82562-231">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-231">String</span></span>|  
|<span data-ttu-id="82562-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-233">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-233">Int32</span></span>|  
|<span data-ttu-id="82562-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="82562-235">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-235">Int32</span></span>|  
|<span data-ttu-id="82562-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="82562-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-237">Boolean</span></span>|  
|<span data-ttu-id="82562-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="82562-239">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-239">String</span></span>|  
|<span data-ttu-id="82562-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="82562-240">IS_NULLABLE</span></span>|<span data-ttu-id="82562-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-241">Boolean</span></span>|  
|<span data-ttu-id="82562-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-242">DATA_TYPE</span></span>|<span data-ttu-id="82562-243">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-243">Int32</span></span>|  
|<span data-ttu-id="82562-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="82562-245">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-245">Int64</span></span>|  
|<span data-ttu-id="82562-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="82562-247">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-247">Int64</span></span>|  
|<span data-ttu-id="82562-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="82562-249">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-249">Int32</span></span>|  
|<span data-ttu-id="82562-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="82562-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="82562-251">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-251">Int16</span></span>|  
|<span data-ttu-id="82562-252">설명</span><span class="sxs-lookup"><span data-stu-id="82562-252">DESCRIPTION</span></span>|<span data-ttu-id="82562-253">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-253">String</span></span>|  
|<span data-ttu-id="82562-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-254">TYPE_NAME</span></span>|<span data-ttu-id="82562-255">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-255">String</span></span>|  
|<span data-ttu-id="82562-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="82562-257">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="82562-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="82562-258">Catalog</span></span>  
  
|<span data-ttu-id="82562-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-259">ColumnName</span></span>|<span data-ttu-id="82562-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-261">CATALOG_NAME</span></span>|<span data-ttu-id="82562-262">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-262">String</span></span>|  
|<span data-ttu-id="82562-263">설명</span><span class="sxs-lookup"><span data-stu-id="82562-263">DESCRIPTION</span></span>|<span data-ttu-id="82562-264">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="82562-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-265">Indexes</span></span>  
  
|<span data-ttu-id="82562-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-266">ColumnName</span></span>|<span data-ttu-id="82562-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-268">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-269">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-269">String</span></span>|  
|<span data-ttu-id="82562-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-271">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-271">String</span></span>|  
|<span data-ttu-id="82562-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-272">TABLE_NAME</span></span>|<span data-ttu-id="82562-273">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-273">String</span></span>|  
|<span data-ttu-id="82562-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-274">INDEX_CATALOG</span></span>|<span data-ttu-id="82562-275">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-275">String</span></span>|  
|<span data-ttu-id="82562-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="82562-277">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-277">String</span></span>|  
|<span data-ttu-id="82562-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-278">INDEX_NAME</span></span>|<span data-ttu-id="82562-279">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-279">String</span></span>|  
|<span data-ttu-id="82562-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="82562-280">PRIMARY_KEY</span></span>|<span data-ttu-id="82562-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-281">Boolean</span></span>|  
|<span data-ttu-id="82562-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="82562-282">UNIQUE</span></span>|<span data-ttu-id="82562-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-283">Boolean</span></span>|  
|<span data-ttu-id="82562-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="82562-284">CLUSTERED</span></span>|<span data-ttu-id="82562-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-285">Boolean</span></span>|  
|<span data-ttu-id="82562-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-286">TYPE</span></span>|<span data-ttu-id="82562-287">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-287">Int32</span></span>|  
|<span data-ttu-id="82562-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="82562-288">FILL_FACTOR</span></span>|<span data-ttu-id="82562-289">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-289">Int32</span></span>|  
|<span data-ttu-id="82562-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="82562-290">INITIAL_SIZE</span></span>|<span data-ttu-id="82562-291">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-291">Int32</span></span>|  
|<span data-ttu-id="82562-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="82562-292">NULLS</span></span>|<span data-ttu-id="82562-293">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-293">Int32</span></span>|  
|<span data-ttu-id="82562-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="82562-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="82562-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-295">Boolean</span></span>|  
|<span data-ttu-id="82562-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="82562-296">AUTO_UPDATE</span></span>|<span data-ttu-id="82562-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-297">Boolean</span></span>|  
|<span data-ttu-id="82562-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-298">NULL_COLLATION</span></span>|<span data-ttu-id="82562-299">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-299">Int32</span></span>|  
|<span data-ttu-id="82562-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-301">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-301">Int64</span></span>|  
|<span data-ttu-id="82562-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-302">COLUMN_NAME</span></span>|<span data-ttu-id="82562-303">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-303">String</span></span>|  
|<span data-ttu-id="82562-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-304">COLUMN_GUID</span></span>|<span data-ttu-id="82562-305">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-305">Guid</span></span>|  
|<span data-ttu-id="82562-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-306">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-307">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-307">Int64</span></span>|  
|<span data-ttu-id="82562-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-308">COLLATION</span></span>|<span data-ttu-id="82562-309">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-309">Int16</span></span>|  
|<span data-ttu-id="82562-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="82562-310">CARDINALITY</span></span>|<span data-ttu-id="82562-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="82562-311">Decimal</span></span>|  
|<span data-ttu-id="82562-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="82562-312">PAGES</span></span>|<span data-ttu-id="82562-313">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-313">Int32</span></span>|  
|<span data-ttu-id="82562-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="82562-314">FILTER_CONDITION</span></span>|<span data-ttu-id="82562-315">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-315">String</span></span>|  
|<span data-ttu-id="82562-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="82562-316">INTEGRATED</span></span>|<span data-ttu-id="82562-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="82562-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="82562-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="82562-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="82562-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="82562-320">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-320">Tables</span></span>  
  
- <span data-ttu-id="82562-321">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-321">Columns</span></span>  
  
- <span data-ttu-id="82562-322">절차</span><span class="sxs-lookup"><span data-stu-id="82562-322">Procedures</span></span>  
  
- <span data-ttu-id="82562-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="82562-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="82562-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="82562-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="82562-325">보기</span><span class="sxs-lookup"><span data-stu-id="82562-325">Views</span></span>  
  
- <span data-ttu-id="82562-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="82562-327">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-327">Tables</span></span>  
  
|<span data-ttu-id="82562-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-328">ColumnName</span></span>|<span data-ttu-id="82562-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-330">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-331">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-331">String</span></span>|  
|<span data-ttu-id="82562-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-333">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-333">String</span></span>|  
|<span data-ttu-id="82562-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-334">TABLE_NAME</span></span>|<span data-ttu-id="82562-335">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-335">String</span></span>|  
|<span data-ttu-id="82562-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-336">TABLE_TYPE</span></span>|<span data-ttu-id="82562-337">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-337">String</span></span>|  
|<span data-ttu-id="82562-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-338">TABLE_GUID</span></span>|<span data-ttu-id="82562-339">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-339">Guid</span></span>|  
|<span data-ttu-id="82562-340">설명</span><span class="sxs-lookup"><span data-stu-id="82562-340">DESCRIPTION</span></span>|<span data-ttu-id="82562-341">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-341">String</span></span>|  
|<span data-ttu-id="82562-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-342">TABLE_PROPID</span></span>|<span data-ttu-id="82562-343">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-343">Int64</span></span>|  
|<span data-ttu-id="82562-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-344">DATE_CREATED</span></span>|<span data-ttu-id="82562-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-345">DateTime</span></span>|  
|<span data-ttu-id="82562-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-346">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="82562-348">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-348">Columns</span></span>  
  
|<span data-ttu-id="82562-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-349">ColumnName</span></span>|<span data-ttu-id="82562-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-351">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-352">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-352">String</span></span>|  
|<span data-ttu-id="82562-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-354">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-354">String</span></span>|  
|<span data-ttu-id="82562-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-355">TABLE_NAME</span></span>|<span data-ttu-id="82562-356">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-356">String</span></span>|  
|<span data-ttu-id="82562-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-357">COLUMN_NAME</span></span>|<span data-ttu-id="82562-358">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-358">String</span></span>|  
|<span data-ttu-id="82562-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-359">COLUMN_GUID</span></span>|<span data-ttu-id="82562-360">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-360">Guid</span></span>|  
|<span data-ttu-id="82562-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-361">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-362">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-362">Int64</span></span>|  
|<span data-ttu-id="82562-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-364">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-364">Int64</span></span>|  
|<span data-ttu-id="82562-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="82562-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-366">Boolean</span></span>|  
|<span data-ttu-id="82562-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="82562-368">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-368">String</span></span>|  
|<span data-ttu-id="82562-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="82562-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="82562-370">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-370">Int64</span></span>|  
|<span data-ttu-id="82562-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="82562-371">IS_NULLABLE</span></span>|<span data-ttu-id="82562-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-372">Boolean</span></span>|  
|<span data-ttu-id="82562-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-373">DATA_TYPE</span></span>|<span data-ttu-id="82562-374">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-374">Int32</span></span>|  
|<span data-ttu-id="82562-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-375">TYPE_GUID</span></span>|<span data-ttu-id="82562-376">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-376">Guid</span></span>|  
|<span data-ttu-id="82562-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="82562-378">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-378">Int64</span></span>|  
|<span data-ttu-id="82562-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="82562-380">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-380">Int64</span></span>|  
|<span data-ttu-id="82562-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="82562-382">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-382">Int32</span></span>|  
|<span data-ttu-id="82562-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="82562-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="82562-384">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-384">Int16</span></span>|  
|<span data-ttu-id="82562-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="82562-386">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-386">Int64</span></span>|  
|<span data-ttu-id="82562-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="82562-388">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-388">String</span></span>|  
|<span data-ttu-id="82562-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="82562-390">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-390">String</span></span>|  
|<span data-ttu-id="82562-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="82562-392">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-392">String</span></span>|  
|<span data-ttu-id="82562-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="82562-394">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-394">String</span></span>|  
|<span data-ttu-id="82562-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="82562-396">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-396">String</span></span>|  
|<span data-ttu-id="82562-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-397">COLLATION_NAME</span></span>|<span data-ttu-id="82562-398">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-398">String</span></span>|  
|<span data-ttu-id="82562-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="82562-400">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-400">String</span></span>|  
|<span data-ttu-id="82562-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="82562-402">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-402">String</span></span>|  
|<span data-ttu-id="82562-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-403">DOMAIN_NAME</span></span>|<span data-ttu-id="82562-404">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-404">String</span></span>|  
|<span data-ttu-id="82562-405">설명</span><span class="sxs-lookup"><span data-stu-id="82562-405">DESCRIPTION</span></span>|<span data-ttu-id="82562-406">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="82562-407">절차</span><span class="sxs-lookup"><span data-stu-id="82562-407">Procedures</span></span>  
  
|<span data-ttu-id="82562-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-408">ColumnName</span></span>|<span data-ttu-id="82562-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="82562-411">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-411">String</span></span>|  
|<span data-ttu-id="82562-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="82562-413">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-413">String</span></span>|  
|<span data-ttu-id="82562-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="82562-415">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-415">String</span></span>|  
|<span data-ttu-id="82562-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="82562-417">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-417">Int16</span></span>|  
|<span data-ttu-id="82562-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="82562-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="82562-419">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-419">String</span></span>|  
|<span data-ttu-id="82562-420">설명</span><span class="sxs-lookup"><span data-stu-id="82562-420">DESCRIPTION</span></span>|<span data-ttu-id="82562-421">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-421">String</span></span>|  
|<span data-ttu-id="82562-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-422">DATE_CREATED</span></span>|<span data-ttu-id="82562-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-423">DateTime</span></span>|  
|<span data-ttu-id="82562-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-424">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="82562-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="82562-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="82562-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-427">ColumnName</span></span>|<span data-ttu-id="82562-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="82562-430">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-430">String</span></span>|  
|<span data-ttu-id="82562-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="82562-432">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-432">String</span></span>|  
|<span data-ttu-id="82562-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="82562-434">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-434">String</span></span>|  
|<span data-ttu-id="82562-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-435">COLUMN_NAME</span></span>|<span data-ttu-id="82562-436">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-436">String</span></span>|  
|<span data-ttu-id="82562-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-437">COLUMN_GUID</span></span>|<span data-ttu-id="82562-438">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-438">Guid</span></span>|  
|<span data-ttu-id="82562-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-439">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-440">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-440">Int64</span></span>|  
|<span data-ttu-id="82562-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="82562-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="82562-442">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-442">Int64</span></span>|  
|<span data-ttu-id="82562-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-444">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-444">Int64</span></span>|  
|<span data-ttu-id="82562-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="82562-445">IS_NULLABLE</span></span>|<span data-ttu-id="82562-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-446">Boolean</span></span>|  
|<span data-ttu-id="82562-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-447">DATA_TYPE</span></span>|<span data-ttu-id="82562-448">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-448">Int32</span></span>|  
|<span data-ttu-id="82562-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-449">TYPE_GUID</span></span>|<span data-ttu-id="82562-450">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-450">Guid</span></span>|  
|<span data-ttu-id="82562-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="82562-452">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-452">Int64</span></span>|  
|<span data-ttu-id="82562-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="82562-454">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-454">Int64</span></span>|  
|<span data-ttu-id="82562-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="82562-456">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-456">Int32</span></span>|  
|<span data-ttu-id="82562-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="82562-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="82562-458">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-458">Int16</span></span>|  
|<span data-ttu-id="82562-459">설명</span><span class="sxs-lookup"><span data-stu-id="82562-459">DESCRIPTION</span></span>|<span data-ttu-id="82562-460">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-460">String</span></span>|  
|<span data-ttu-id="82562-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="82562-461">OVERLOAD</span></span>|<span data-ttu-id="82562-462">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="82562-463">보기</span><span class="sxs-lookup"><span data-stu-id="82562-463">Views</span></span>  
  
|<span data-ttu-id="82562-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-464">ColumnName</span></span>|<span data-ttu-id="82562-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-466">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-467">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-467">String</span></span>|  
|<span data-ttu-id="82562-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-469">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-469">String</span></span>|  
|<span data-ttu-id="82562-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-470">TABLE_NAME</span></span>|<span data-ttu-id="82562-471">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-471">String</span></span>|  
|<span data-ttu-id="82562-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="82562-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="82562-473">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-473">String</span></span>|  
|<span data-ttu-id="82562-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="82562-474">CHECK_OPTION</span></span>|<span data-ttu-id="82562-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-475">Boolean</span></span>|  
|<span data-ttu-id="82562-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="82562-476">IS_UPDATABLE</span></span>|<span data-ttu-id="82562-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-477">Boolean</span></span>|  
|<span data-ttu-id="82562-478">설명</span><span class="sxs-lookup"><span data-stu-id="82562-478">DESCRIPTION</span></span>|<span data-ttu-id="82562-479">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-479">String</span></span>|  
|<span data-ttu-id="82562-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-480">DATE_CREATED</span></span>|<span data-ttu-id="82562-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-481">DateTime</span></span>|  
|<span data-ttu-id="82562-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-482">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="82562-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-484">Indexes</span></span>  
  
|<span data-ttu-id="82562-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-485">ColumnName</span></span>|<span data-ttu-id="82562-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-487">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-488">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-488">String</span></span>|  
|<span data-ttu-id="82562-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-490">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-490">String</span></span>|  
|<span data-ttu-id="82562-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-491">TABLE_NAME</span></span>|<span data-ttu-id="82562-492">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-492">String</span></span>|  
|<span data-ttu-id="82562-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-493">INDEX_CATALOG</span></span>|<span data-ttu-id="82562-494">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-494">String</span></span>|  
|<span data-ttu-id="82562-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="82562-496">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-496">String</span></span>|  
|<span data-ttu-id="82562-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-497">INDEX_NAME</span></span>|<span data-ttu-id="82562-498">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-498">String</span></span>|  
|<span data-ttu-id="82562-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="82562-499">PRIMARY_KEY</span></span>|<span data-ttu-id="82562-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-500">Boolean</span></span>|  
|<span data-ttu-id="82562-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="82562-501">UNIQUE</span></span>|<span data-ttu-id="82562-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-502">Boolean</span></span>|  
|<span data-ttu-id="82562-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="82562-503">CLUSTERED</span></span>|<span data-ttu-id="82562-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-504">Boolean</span></span>|  
|<span data-ttu-id="82562-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-505">TYPE</span></span>|<span data-ttu-id="82562-506">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-506">Int32</span></span>|  
|<span data-ttu-id="82562-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="82562-507">FILL_FACTOR</span></span>|<span data-ttu-id="82562-508">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-508">Int32</span></span>|  
|<span data-ttu-id="82562-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="82562-509">INITIAL_SIZE</span></span>|<span data-ttu-id="82562-510">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-510">Int32</span></span>|  
|<span data-ttu-id="82562-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="82562-511">NULLS</span></span>|<span data-ttu-id="82562-512">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-512">Int32</span></span>|  
|<span data-ttu-id="82562-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="82562-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="82562-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-514">Boolean</span></span>|  
|<span data-ttu-id="82562-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="82562-515">AUTO_UPDATE</span></span>|<span data-ttu-id="82562-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-516">Boolean</span></span>|  
|<span data-ttu-id="82562-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-517">NULL_COLLATION</span></span>|<span data-ttu-id="82562-518">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-518">Int32</span></span>|  
|<span data-ttu-id="82562-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-520">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-520">Int64</span></span>|  
|<span data-ttu-id="82562-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-521">COLUMN_NAME</span></span>|<span data-ttu-id="82562-522">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-522">String</span></span>|  
|<span data-ttu-id="82562-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-523">COLUMN_GUID</span></span>|<span data-ttu-id="82562-524">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-524">Guid</span></span>|  
|<span data-ttu-id="82562-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-525">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-526">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-526">Int64</span></span>|  
|<span data-ttu-id="82562-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-527">COLLATION</span></span>|<span data-ttu-id="82562-528">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-528">Int16</span></span>|  
|<span data-ttu-id="82562-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="82562-529">CARDINALITY</span></span>|<span data-ttu-id="82562-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="82562-530">Decimal</span></span>|  
|<span data-ttu-id="82562-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="82562-531">PAGES</span></span>|<span data-ttu-id="82562-532">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-532">Int32</span></span>|  
|<span data-ttu-id="82562-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="82562-533">FILTER_CONDITION</span></span>|<span data-ttu-id="82562-534">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-534">String</span></span>|  
|<span data-ttu-id="82562-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="82562-535">INTEGRATED</span></span>|<span data-ttu-id="82562-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="82562-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="82562-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="82562-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="82562-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="82562-539">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-539">Tables</span></span>  
  
- <span data-ttu-id="82562-540">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-540">Columns</span></span>  
  
- <span data-ttu-id="82562-541">절차</span><span class="sxs-lookup"><span data-stu-id="82562-541">Procedures</span></span>  
  
- <span data-ttu-id="82562-542">보기</span><span class="sxs-lookup"><span data-stu-id="82562-542">Views</span></span>  
  
- <span data-ttu-id="82562-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="82562-544">Tables</span><span class="sxs-lookup"><span data-stu-id="82562-544">Tables</span></span>  
  
|<span data-ttu-id="82562-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-545">ColumnName</span></span>|<span data-ttu-id="82562-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-547">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-548">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-548">String</span></span>|  
|<span data-ttu-id="82562-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-550">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-550">String</span></span>|  
|<span data-ttu-id="82562-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-551">TABLE_NAME</span></span>|<span data-ttu-id="82562-552">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-552">String</span></span>|  
|<span data-ttu-id="82562-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-553">TABLE_TYPE</span></span>|<span data-ttu-id="82562-554">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-554">String</span></span>|  
|<span data-ttu-id="82562-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-555">TABLE_GUID</span></span>|<span data-ttu-id="82562-556">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-556">Guid</span></span>|  
|<span data-ttu-id="82562-557">설명</span><span class="sxs-lookup"><span data-stu-id="82562-557">DESCRIPTION</span></span>|<span data-ttu-id="82562-558">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-558">String</span></span>|  
|<span data-ttu-id="82562-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-559">TABLE_PROPID</span></span>|<span data-ttu-id="82562-560">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-560">Int64</span></span>|  
|<span data-ttu-id="82562-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-561">DATE_CREATED</span></span>|<span data-ttu-id="82562-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-562">DateTime</span></span>|  
|<span data-ttu-id="82562-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-563">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="82562-565">Columns</span><span class="sxs-lookup"><span data-stu-id="82562-565">Columns</span></span>  
  
|<span data-ttu-id="82562-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-566">ColumnName</span></span>|<span data-ttu-id="82562-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-568">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-569">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-569">String</span></span>|  
|<span data-ttu-id="82562-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-571">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-571">String</span></span>|  
|<span data-ttu-id="82562-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-572">TABLE_NAME</span></span>|<span data-ttu-id="82562-573">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-573">String</span></span>|  
|<span data-ttu-id="82562-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-574">COLUMN_NAME</span></span>|<span data-ttu-id="82562-575">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-575">String</span></span>|  
|<span data-ttu-id="82562-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-576">COLUMN_GUID</span></span>|<span data-ttu-id="82562-577">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-577">Guid</span></span>|  
|<span data-ttu-id="82562-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-578">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-579">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-579">Int64</span></span>|  
|<span data-ttu-id="82562-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-581">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-581">Int64</span></span>|  
|<span data-ttu-id="82562-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="82562-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-583">Boolean</span></span>|  
|<span data-ttu-id="82562-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="82562-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="82562-585">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-585">String</span></span>|  
|<span data-ttu-id="82562-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="82562-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="82562-587">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-587">Int64</span></span>|  
|<span data-ttu-id="82562-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="82562-588">IS_NULLABLE</span></span>|<span data-ttu-id="82562-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-589">Boolean</span></span>|  
|<span data-ttu-id="82562-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-590">DATA_TYPE</span></span>|<span data-ttu-id="82562-591">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-591">Int32</span></span>|  
|<span data-ttu-id="82562-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-592">TYPE_GUID</span></span>|<span data-ttu-id="82562-593">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-593">Guid</span></span>|  
|<span data-ttu-id="82562-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="82562-595">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-595">Int64</span></span>|  
|<span data-ttu-id="82562-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="82562-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="82562-597">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-597">Int64</span></span>|  
|<span data-ttu-id="82562-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="82562-599">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-599">Int32</span></span>|  
|<span data-ttu-id="82562-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="82562-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="82562-601">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-601">Int16</span></span>|  
|<span data-ttu-id="82562-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="82562-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="82562-603">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-603">Int64</span></span>|  
|<span data-ttu-id="82562-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="82562-605">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-605">String</span></span>|  
|<span data-ttu-id="82562-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="82562-607">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-607">String</span></span>|  
|<span data-ttu-id="82562-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="82562-609">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-609">String</span></span>|  
|<span data-ttu-id="82562-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="82562-611">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-611">String</span></span>|  
|<span data-ttu-id="82562-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="82562-613">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-613">String</span></span>|  
|<span data-ttu-id="82562-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-614">COLLATION_NAME</span></span>|<span data-ttu-id="82562-615">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-615">String</span></span>|  
|<span data-ttu-id="82562-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="82562-617">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-617">String</span></span>|  
|<span data-ttu-id="82562-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="82562-619">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-619">String</span></span>|  
|<span data-ttu-id="82562-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-620">DOMAIN_NAME</span></span>|<span data-ttu-id="82562-621">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-621">String</span></span>|  
|<span data-ttu-id="82562-622">설명</span><span class="sxs-lookup"><span data-stu-id="82562-622">DESCRIPTION</span></span>|<span data-ttu-id="82562-623">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="82562-624">절차</span><span class="sxs-lookup"><span data-stu-id="82562-624">Procedures</span></span>  
  
|<span data-ttu-id="82562-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-625">ColumnName</span></span>|<span data-ttu-id="82562-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="82562-628">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-628">String</span></span>|  
|<span data-ttu-id="82562-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="82562-630">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-630">String</span></span>|  
|<span data-ttu-id="82562-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="82562-632">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-632">String</span></span>|  
|<span data-ttu-id="82562-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="82562-634">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-634">Int16</span></span>|  
|<span data-ttu-id="82562-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="82562-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="82562-636">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-636">String</span></span>|  
|<span data-ttu-id="82562-637">설명</span><span class="sxs-lookup"><span data-stu-id="82562-637">DESCRIPTION</span></span>|<span data-ttu-id="82562-638">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-638">String</span></span>|  
|<span data-ttu-id="82562-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-639">DATE_CREATED</span></span>|<span data-ttu-id="82562-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-640">DateTime</span></span>|  
|<span data-ttu-id="82562-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-641">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="82562-643">보기</span><span class="sxs-lookup"><span data-stu-id="82562-643">Views</span></span>  
  
|<span data-ttu-id="82562-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-644">ColumnName</span></span>|<span data-ttu-id="82562-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-646">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-647">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-647">String</span></span>|  
|<span data-ttu-id="82562-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-649">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-649">String</span></span>|  
|<span data-ttu-id="82562-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-650">TABLE_NAME</span></span>|<span data-ttu-id="82562-651">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-651">String</span></span>|  
|<span data-ttu-id="82562-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="82562-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="82562-653">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-653">String</span></span>|  
|<span data-ttu-id="82562-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="82562-654">CHECK_OPTION</span></span>|<span data-ttu-id="82562-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-655">Boolean</span></span>|  
|<span data-ttu-id="82562-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="82562-656">IS_UPDATABLE</span></span>|<span data-ttu-id="82562-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-657">Boolean</span></span>|  
|<span data-ttu-id="82562-658">설명</span><span class="sxs-lookup"><span data-stu-id="82562-658">DESCRIPTION</span></span>|<span data-ttu-id="82562-659">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-659">String</span></span>|  
|<span data-ttu-id="82562-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="82562-660">DATE_CREATED</span></span>|<span data-ttu-id="82562-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-661">DateTime</span></span>|  
|<span data-ttu-id="82562-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="82562-662">DATE_MODIFIED</span></span>|<span data-ttu-id="82562-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="82562-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="82562-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="82562-664">Indexes</span></span>  
  
|<span data-ttu-id="82562-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="82562-665">ColumnName</span></span>|<span data-ttu-id="82562-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="82562-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="82562-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-667">TABLE_CATALOG</span></span>|<span data-ttu-id="82562-668">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-668">String</span></span>|  
|<span data-ttu-id="82562-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="82562-670">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-670">String</span></span>|  
|<span data-ttu-id="82562-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-671">TABLE_NAME</span></span>|<span data-ttu-id="82562-672">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-672">String</span></span>|  
|<span data-ttu-id="82562-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82562-673">INDEX_CATALOG</span></span>|<span data-ttu-id="82562-674">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-674">String</span></span>|  
|<span data-ttu-id="82562-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82562-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="82562-676">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-676">String</span></span>|  
|<span data-ttu-id="82562-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-677">INDEX_NAME</span></span>|<span data-ttu-id="82562-678">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-678">String</span></span>|  
|<span data-ttu-id="82562-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="82562-679">PRIMARY_KEY</span></span>|<span data-ttu-id="82562-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-680">Boolean</span></span>|  
|<span data-ttu-id="82562-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="82562-681">UNIQUE</span></span>|<span data-ttu-id="82562-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-682">Boolean</span></span>|  
|<span data-ttu-id="82562-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="82562-683">CLUSTERED</span></span>|<span data-ttu-id="82562-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-684">Boolean</span></span>|  
|<span data-ttu-id="82562-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="82562-685">TYPE</span></span>|<span data-ttu-id="82562-686">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-686">Int32</span></span>|  
|<span data-ttu-id="82562-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="82562-687">FILL_FACTOR</span></span>|<span data-ttu-id="82562-688">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-688">Int32</span></span>|  
|<span data-ttu-id="82562-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="82562-689">INITIAL_SIZE</span></span>|<span data-ttu-id="82562-690">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-690">Int32</span></span>|  
|<span data-ttu-id="82562-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="82562-691">NULLS</span></span>|<span data-ttu-id="82562-692">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-692">Int32</span></span>|  
|<span data-ttu-id="82562-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="82562-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="82562-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-694">Boolean</span></span>|  
|<span data-ttu-id="82562-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="82562-695">AUTO_UPDATE</span></span>|<span data-ttu-id="82562-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-696">Boolean</span></span>|  
|<span data-ttu-id="82562-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-697">NULL_COLLATION</span></span>|<span data-ttu-id="82562-698">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-698">Int32</span></span>|  
|<span data-ttu-id="82562-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="82562-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="82562-700">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-700">Int64</span></span>|  
|<span data-ttu-id="82562-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82562-701">COLUMN_NAME</span></span>|<span data-ttu-id="82562-702">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-702">String</span></span>|  
|<span data-ttu-id="82562-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="82562-703">COLUMN_GUID</span></span>|<span data-ttu-id="82562-704">Guid</span><span class="sxs-lookup"><span data-stu-id="82562-704">Guid</span></span>|  
|<span data-ttu-id="82562-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="82562-705">COLUMN_PROPID</span></span>|<span data-ttu-id="82562-706">Int64</span><span class="sxs-lookup"><span data-stu-id="82562-706">Int64</span></span>|  
|<span data-ttu-id="82562-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="82562-707">COLLATION</span></span>|<span data-ttu-id="82562-708">Int16</span><span class="sxs-lookup"><span data-stu-id="82562-708">Int16</span></span>|  
|<span data-ttu-id="82562-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="82562-709">CARDINALITY</span></span>|<span data-ttu-id="82562-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="82562-710">Decimal</span></span>|  
|<span data-ttu-id="82562-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="82562-711">PAGES</span></span>|<span data-ttu-id="82562-712">Int32</span><span class="sxs-lookup"><span data-stu-id="82562-712">Int32</span></span>|  
|<span data-ttu-id="82562-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="82562-713">FILTER_CONDITION</span></span>|<span data-ttu-id="82562-714">문자열</span><span class="sxs-lookup"><span data-stu-id="82562-714">String</span></span>|  
|<span data-ttu-id="82562-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="82562-715">INTEGRATED</span></span>|<span data-ttu-id="82562-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="82562-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82562-717">참고자료</span><span class="sxs-lookup"><span data-stu-id="82562-717">See also</span></span>

- [<span data-ttu-id="82562-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="82562-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
