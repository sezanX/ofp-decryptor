## OFP Decrypter by [SEZAN-X](https://github.com/sezanX/)

**OFP Decrypter** is a GitHub Actions workflow designed to decrypt OPPO Firmware Package (OFP) files. It supports both Qualcomm (QC) and MediaTek (MTK) OFP formats. The decrypted files are zipped and uploaded to your SourceForge directory for easy access.

## Features
- Supports both QC and MTK OFP file decryption.
- Automatically handles large files (>8GB) with environment cleanup.
- Uploads decrypted files to SourceForge for sharing or storage.


## Prerequisites
1. **GitHub Repository**:
   - Ensure this workflow is added to `.github/workflows/` in your repository.
2. **SourceForge Account**:
   - Add the following secrets in your repository:
     - `SFUSER`: Your SourceForge username.
     - `SFPASS`: Your SourceForge password.
     - `SFDIR`: Directory name for uploading files on SourceForge.

## Inputs
| Name       | Description                             | Default | Required |
|------------|-----------------------------------------|---------|----------|
| `ofp_link` | The direct download link for the OFP file. | -       | Yes      |
| `bigfile`  | Set to `YES` if the OFP file is >8GB.    | `NO`    | No       |

## Output
- A decrypted ZIP file containing the extracted firmware files, available at:
  ```
  https://sourceforge.net/projects/<SFDIR>/<OFP_NAME>/Decrypted.<OFP_NAME>.zip
  ```

## Usage
1. **Run Workflow**:
   - Navigate to your repository's **Actions** tab.
   - Select the **OFP Decrypter by SEZAN-X** workflow.
   - Provide the following inputs:
     - `ofp_link`: The URL to the OFP file.
     - `bigfile`: Optional; set to "YES" if the file is large (>8GB).

2. **Monitor Progress**:
   - Watch the workflow logs to check the progress.

3. **Download Output**:
   - After completion, the decrypted files will be uploaded to SourceForge. The download link will be shown in the logs.

## Example Input
- `ofp_link`: `https://example.com/path/to/firmware.ofp`
- `bigfile`: `NO`

## License
Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.  
You may obtain a copy of the License at:

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

