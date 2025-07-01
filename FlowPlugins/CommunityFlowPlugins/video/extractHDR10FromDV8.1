module.exports.details = {
  name: 'DV 8.1 HEVC to HDR10 MKV (no transcode, strips DV)',
  type: 'video',
  operation: 'transcode',
  description: 'Repackage DV 8.1 HEVC input as HDR10-only MKV by removing DV RPU (no transcoding).',
  version: '1.0',
  author: 'copilot'
};

module.exports.plugin = function (file, librarySettings, inputs, otherArguments) {
  const path = require('path');
  const basename = path.parse(file.input).name;
  const dir = path.dirname(file.input);

  const vid = path.join(dir, `${basename}_vid.hevc`);
  const vid_clean = path.join(dir, `${basename}_vid_hdr10.hevc`);
  const out = path.join(dir, `${basename}_HDR10.mkv`);

  return {
    // Step 1: Extract HEVC video stream
    // Step 2: Remove DV RPU using dovi_tool
    // Step 3: Remux cleaned video with original audio/subs as MKV
    ffmpegCommand: `
      ffmpeg -y -i "${file.input}" -map 0:v:0 -c copy "${vid}" && \
      dovi_tool remux --remove --input "${vid}" --output "${vid_clean}" && \
      ffmpeg -y -i "${vid_clean}" -i "${file.input}" -map 0:v:0 -map 1:a? -map 1:s? -c copy "${out}"
    `,
    outputFile: out,
    infoLog: 'DV RPU removed from HEVC, repackaged as HDR10-only MKV.'
  };
};
