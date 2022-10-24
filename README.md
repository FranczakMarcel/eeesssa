# eeesssa

function count_smileys($arr): int {
  $allow_eyes  = [':', ';'];
  $allow_nouse  = ['-', '~'];
  $allow_mouth  = [')', 'D'];
  $count = 0;
  
  foreach ($arr as $a) {
    $parts = str_split($a);
    if (!in_array($parts[0], $allow_eyes)) {
      continue;
    }
    if (count($parts) == 3) {
      if (!in_array($parts[1], $allow_nouse)) {
      continue;
      }
      
      if (!in_array($parts[2], $allow_mouth)) {
        continue;
      }
    } else {
      if (!in_array($parts[1], $allow_mouth)) {
        continue;
      }
    }
    
    $count++;
  }
  
  return $count;
  
}
