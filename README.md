# darshanaps.github.io
Portfolio


# Edit the below to adjust the "ಕ" alignment in the language toggle
# transform: translate(calc(-43% + 1.14px), calc(-50% - 2.10px));

=======


<!-- ===== Voices strip: Kannada names ===== -->
<script>
(function () {
  // Keys must match the English text in the cards exactly.
  var KN_NAMES = {
    'Margot Robbie':        'ಮಾರ್ಗೋಟ್ ರಾಬಿ',
    'Samantha Ruth Prabhu': 'ಸಮಂತಾ ರುತ್ ಪ್ರಭು',
    'Raveena Tandon':       'ರವೀನಾ ಟಂಡನ್',
    'Wamiqa Gabbi':         'ವಾಮಿಕಾ ಗಬ್ಬಿ',
    'Nimisha Sajayan':      'ನಿಮಿಷಾ ಸಜಯನ್',
    'Ramya Nambessan':      'ರಮ್ಯಾ ನಂಬೀಶನ್',
    'Varu Sharathkumar':    'ವರು ಶರತ್‌ಕುಮಾರ್',
    'Sania Mirza':          'ಸಾನಿಯಾ ಮಿರ್ಜಾ',
    'Anaswara Rajan':       'ಅನಸ್ವರಾ ರಾಜನ್'
  };

  var KN_PROJECTS = {
    'Barbie':                'ಬಾರ್ಬಿ',
    'Citadel: Honey Bunny':  'ಸಿಟಾಡೆಲ್: ಹನಿ ಬನ್ನಿ',
    'Karma Calling':         'ಕರ್ಮ ಕಾಲಿಂಗ್',
    'Jubilee':               'ಜುಬಿಲಿ',
    'Poacher':               'ಪೋಚರ್',
    'Dayaa':                 'ದಯಾ',
    'Hanu-Man':              'ಹನು-ಮಾನ್',
    'Centuary Mattress':     'ಸೆಂಚುರಿ ಮ್ಯಾಟ್ರೆಸ್',
    'Kalyan Jewellers':      'ಕಲ್ಯಾಣ್ ಜ್ಯುವೆಲರ್ಸ್'
  };

  try {
    // Stash the English text once, so switching back is exact rather than a
    // reverse lookup (two actors could share a project title).
    var fields = document.querySelectorAll('.voice-name, .voice-project');
    if (!fields.length) return;

    Array.prototype.forEach.call(fields, function (el) {
      if (!el.hasAttribute('data-en')) {
        el.setAttribute('data-en', el.textContent.trim());
      }
    });

    function apply(lang) {
      Array.prototype.forEach.call(fields, function (el) {
        var en = el.getAttribute('data-en');
        var map = el.classList.contains('voice-name') ? KN_NAMES : KN_PROJECTS;
        // Fall back to English for anything not in the map, so a missing
        // entry shows the original rather than going blank.
        el.textContent = (lang === 'kn' && map[en]) ? map[en] : en;
      });
    }

    document.querySelectorAll('.lang-option').forEach(function (btn) {
      btn.addEventListener('click', function () {
        apply(btn.getAttribute('data-lang'));
      });
    });

    // Respect whichever button is already active on load
    var active = document.querySelector('.lang-option.active');
    if (active) apply(active.getAttribute('data-lang'));
  } catch (err) {
    console.error('[voices] Kannada names disabled:', err);
  }
})();
</script>